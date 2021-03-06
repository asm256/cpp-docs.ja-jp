---
title: "Ref クラスと構造体 (C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
caps.latest.revision: 42
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 42
---
# Ref クラスと構造体 (C++-CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) は、ユーザー定義の *ref クラス*および *ref 構造体*と、ユーザー定義の*値クラス*および*値構造体*をサポートします。 これらのデータ構造体は、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] が [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型システムをサポートするための主コンテナーです。 それらのコンテンツは、特定の規則に従ってメタデータに出力されます。これにより、それらのコンテンツを C\+\+ やその他の言語で記述された [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリと [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] コンポーネントとの間で渡すことができるようになります。  
  
 ref クラスまたは ref 構造体には、次のような固有の特徴があります。  
  
-   名前空間内部で宣言される必要があり、名前空間のスコープ、およびその名前空間内で public または private のアクセシビリティを持つことができます。 パブリック型だけがメタデータに出力されます。 入れ子になったパブリック[列挙型](../cppcx/enums-c-cx.md)クラスを含め、入れ子になったパブリック クラス定義は使用できません。 詳細については、「[名前空間と型の参照範囲](../cppcx/namespaces-and-type-visibility-c-cx.md)」を参照してください。  
  
-   メンバーとして、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] の ref クラス、値クラス、ref 構造体、null 許容の値構造体などを格納できます。 これには、float64 や bool などのスカラー型も含まれる場合があります。 また、パブリックでない限り `std::vector` やカスタム クラスなどの標準の C\+\+ 型が含まれる場合もあります。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コンストラクトは、`public`、`protected`、`internal`、`private`、または `protected private` のアクセシビリティを持つことができます。`public` または `protected` のすべてのメンバーは、メタデータに出力されます。 標準 C\+\+ の型は、`private`、`internal`、または `protected private` のアクセシビリティを持つ必要があります。これにより、それらの型がメタデータに出力されることが防止されます。  
  
-   1 つ以上の*インターフェイス クラス*または*インターフェイス構造体*を実装することができます。  
  
-   1 つの基底クラスから継承することができ、基底クラス自体に追加の制限があります。 パブリック ref クラス階層構造での継承には、private ref クラスでの継承によりも多くの制限があります。  
  
-   generic として宣言することはできません。 private アクセシビリティがある場合、テンプレートになることができます。  
  
-   その有効期間は、自動参照カウントによって管理されます。  
  
## 宣言  
 次のコード片は `Person` ref クラスを宣言します。 C\+\+ の標準の `std::map` 型がプライベート メンバーで使用され、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IMapView` インターフェイスがパブリック インターフェイスで使用されていることに注意してください。 また、"^" が参照型の宣言に追加されることにも注意してください。  
  
 [!code-cpp[cx_classes#03](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#03)]  
  
## 実装  
 このコード例は、`Person` ref クラスの実装を示しています。  
  
 [!code-cpp[cx_classes#04](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#04)]  
  
## 使用方法  
 次のコード例は、クライアント コードで `Person` ref クラスを使用する方法を示しています。  
  
 [!code-cpp[cx_classes#05](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#05)]  
  
 また、スタック セマンティクスを使用して ref クラスのローカル変数を宣言することもできます。 メモリはまだ動的に割り当てられますが、このようなオブジェクトはスタック ベースの変数のように動作します。 1 つの重要な違いは、スタック セマンティクスを使用して宣言されている変数に追跡参照 \(%\) を割り当てることができないことです。これにより、関数が終了したときに参照カウントが必ず 0 にデクリメントされます。 この例では、基本 ref クラス `Uri`、およびスタック セマンティクスでそれを使用する関数を示します。  
  
 [!code-cpp[cx_classes#06](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#06)]  
  
## メモリ管理  
 ref クラスは、`ref new` キーワードを使用して動的メモリに割り当てます。  
  
 [!code-cpp[cx_classes#01](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#01)]  
  
 オブジェクトへのハンドル演算子 ^ は "キャレット" として知られ、基本的には C\+\+ スマート ポインターです。 これが指すメモリは、最後のキャレットがスコープ外に出ると自動的に破棄されるか、明示的に `nullptr` に設定されます。  
  
 定義上、ref クラスには、参照セマンティクスがあります。 ref クラスの変数を代入した場合、代入されるのはコピーされるハンドルであり、オブジェクト自体ではありません。 次の例では、代入後に `myClass` と `myClass2` の両方が同じメモリ位置を指します。  
  
 [!code-cpp[cx_classes#02](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#02)]  
  
 C\+\+\/CX ref クラスをインスタンス化する場合、コンストラクターを呼び出す前にメモリがゼロ初期化されます。したがって、プロパティを含む個々のメンバーをゼロ初期化する必要はありません。 C\+\+\/CX クラスが Windows ランタイム C\+\+ ライブラリ \(WRL\) クラスから派生している場合、C\+\+\/CX 派生クラスの部分だけがゼロ初期化されます。  
  
## メンバー  
 ref クラスは、`public`、`protected`、および `private` の関数メンバーを格納できます。`public` と `protected` のメンバーだけが、メタデータに出力されます。 入れ子になったクラスおよび ref クラスは許可されますが、`public` になることはできません。 public フィールドは使用できません。public データ メンバーはプロパティとして宣言する必要があります。 プライベートまたはプロテクトの内部データ メンバーは、フィールドである場合があります。 既定では、ref クラスでは、すべてのメンバーのアクセシビリティは `private` です。  
  
 ref 構造体は ref クラスと同じですが、既定ではメンバーのアクセシビリティは `public` です。  
  
 `public` の ref クラスまたは ref 構造体は、メタデータに出力されますが、他の [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリおよび [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントから使用できるようにするには、public または protected のコンストラクターが少なくとも 1 つは必要です。 public コンストラクターを持つ public ref クラスは、アプリケーション バイナリ インターフェイス \(ABI: Application Binary Interface\) を介してさらに派生されることを防ぐために `sealed` としても宣言される必要があります。  
  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型システムが定数をサポートしていないため、パブリック メンバーを定数として宣言することはできません。 静的なプロパティを使用して、定数値を持つパブリック データ メンバーを宣言することができます。  
  
 public の ref クラスまたは構造体が定義されると、コンパイラは必要な属性をクラスに適用し、その情報をアプリの .winmd ファイルに格納します。 ただし、public unsealed の ref クラスを定義するときは、`Windows::Foundation::Metadata::WebHostHidden` 属性を手動で適用して、クラスが JavaScript で記述された [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリからは確実に見えないようにしてください。  
  
 ref クラスは、`const` 型を含む標準 C\+\+ の型を、`private`、`internal`、または `protected private` のあらゆるメンバーの中で使用することができます。  
  
 型パラメーターを持つパブリック ref クラスは許可されません。 ユーザー定義の generic ref クラスは許可されません。 private、internal、または protected private の ref クラスは、テンプレートになることができます。  
  
## デストラクター  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] では、パブリック デストラクターで `delete` を呼び出すと、オブジェクトの参照カウントに関係なくデストラクターが呼び出されます。 この動作により、非 RAII リソースのカスタム クリーンアップを確定的な方法で実行できるデストラクターを定義できます。 ただし、この場合でも、オブジェクト自体はメモリから削除されません。 オブジェクトのメモリは、参照カウントがゼロに達した場合のみ解放されます。  
  
 クラスのデストラクターがパブリックでない場合は、参照カウントがゼロに達する場合にのみ、このデストラクターが呼び出されます。 プライベート デストラクターを持つオブジェクトに対して `delete` を呼び出すと、コンパイラで警告 C4493 が発生し、"\<型名\> のデストラクターには 'public' アクセシビリティが設定されていないので、削除式の影響はありません" というメッセージが返されます。  
  
 Ref クラスのデストラクターでは、次以外の宣言はできません。  
  
-   public および virtual \(sealed または unsealed 型で使用できます\)  
  
-   protected private と non\-virtual \(unsealed 型でのみ使用できます\)  
  
-   private と non\-virtual \(sealed 型でのみ使用できます\)  
  
 アクセシビリティ、仮想性、およびシールド性のこれ以外の組み合わせは使用できません。  デストラクターが明示的に宣言されない場合、型の基底クラスまたはメンバーに public デストラクターがあると、コンパイラは public virtual デストラクターを生成します。 それ以外の場合、コンパイラは unsealed 型には protected private non\-virtual デストラクター、sealed 型には private non\-virtual デストラクターを生成します。  
  
 デストラクターを既に実行しているクラスのメンバーにアクセスを試みたときの動作は不確定です。プログラムがクラッシュする可能性が高いと思われます。 public デストラクターがない型上で `delete t` を呼び出しても、何の効果もありません。 型の階層構造内から既知の `delete this` または `private` デストラクターを持つ型または基底クラス上で `protected private` を呼び出しても、何の効果もありません。  
  
 public デストラクターが宣言されると、コンパイラがコードを生成するので、ref クラスが `Platform::IDisposable` を実装し、デストラクターが `Dispose` メソッドを実装します。`Platform::IDisposable` は、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] の `Windows::Foundation::IClosable` プロジェクションです。 これらのインターフェイスは、明示的に実装しないでください。  
  
## 継承  
 Platform::Object は、すべての ref クラスの汎用基底クラスです。 ref クラスは、いずれも Platform::Object に暗黙的に変換可能で、[Object::ToString](../cppcx/object-tostring-method-c-cx.md) をオーバーライドできます。 ただし、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 継承モデルは、一般的な継承モデルとして使用されません。つまり、C\+\+\/CX では、ユーザー定義のパブリック ref クラスは基底クラスとして使用できません。  
  
 XAML ユーザー コントロールを作成し、オブジェクトが依存関係プロパティ システムに参加している場合は、`Windows::UI::Xaml::DependencyObject` を基底クラスとして使用できます。  
  
 `MyBase` から継承する unsealed クラス `DependencyObject` が定義されると、コンポーネントまたはアプリ内の他の public または private の ref クラスは `MyBase` から継承できるようになります。 public ref クラスの継承は、仮想メソッド、ポリモーフィック ID、およびカプセル化のオーバーライドをサポートする目的以外には実行しないでください。  
  
 private 基本 ref クラスがなくても、既存の unsealed クラスから派生できます。 独自のプログラム構造をモデル化するかまたはコードの再利用を有効にするために、オブジェクト階層構造を必要とする場合は、private または internal の ref クラスを使用するか、さらに優れた手法として標準 C\+\+ クラスを使用してください。 public sealed ref クラス ラッパーを通じて、プライベート オブジェクト階層構造の機能を公開できます。  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] に public または protected のコンストラクターを持つ ref クラスは、sealed として宣言する必要があります。 この制限があるため、C\# や Visual Basic などの他の言語で記述されたクラスの場合、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] で記述された [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コンポーネントで宣言する型から継承する方法はありません。  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] で継承するための基本的な規則を次に示します。  
  
-   ref クラスは多くても 1 つの基本 ref クラスからしか直接継承できませんが、任意の数のインターフェイスを実装できます。  
  
-   あるクラスに public コンストラクターがある場合、さらに派生されることを防ぐために sealed として宣言する必要があります。  
  
-   基底クラスが `Windows::UI::Xaml::DependencyObject` などの既存の unsealed 基底クラスから直接または間接的に派生する場合は、internal または protected private のコンストラクターを持つ public unsealed 基底クラスを作成できます。 .winmd ファイル間でのユーザー定義 ref クラスの継承はサポートされません。ただし、ref クラスは別の .winmd ファイルで定義されているインターフェイスから継承できます。 同じ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントまたは [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリ内でのみ、ユーザー定義基本 ref クラスから派生クラスを作成できます。  
  
-   ref クラスの場合、パブリック継承のみサポートされます。  
  
     [!code-cpp[cx_classes#08](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#08)]  
  
 次の例では、継承階層構造の他の ref クラスから派生する public ref クラスを公開する方法を示します。  
  
 [!code-cpp[cx_classes#09](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#09)]  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [値クラスと構造体](../cppcx/value-classes-and-structs-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)