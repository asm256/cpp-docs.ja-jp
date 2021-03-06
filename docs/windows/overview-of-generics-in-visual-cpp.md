---
title: "Overview of Generics in Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generics [C++], about generics"
  - "default initializers [C++]"
  - "type parameters [C++]"
  - "constructed types"
  - "type arguments [C++]"
  - "constructed types, open [C++]"
  - "open constructed types [C++]"
  - "constructed types, closed [C++]"
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Overview of Generics in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ジェネリックは、共通言語ランタイムによってサポートされるパラメーター化された型です。  パラメーター化された型は、ジェネリックを使用するときに指定できる未知の型パラメーターで定義されている型です。  
  
## 理由ジェネリックか。  
 C\+\+ サポート テンプレートは、ジェネリックの型指定されたコレクションのクラスを作成するには、パラメーター化された型をサポートします。  ただし、テンプレートはコンパイル時パラメーター化できます。  テンプレート定義を含むアセンブリを参照し、テンプレートの新しいクラスを作成することはできません。  コンパイルされて、特殊なテンプレートは他のクラスまたはメソッドのように見えます。  これに対し、ジェネリックは、パラメーター化された型になるようにランタイムがわかっている場合は、パラメーター化された型として MSIL で終了; ジェネリック型を含むアセンブリを参照するソース・コードをジェネリック型の特殊化を作成できます。  Visual C\+\+ のテンプレートとジェネリック比較の詳細については、「[Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md)」を参照してください。  
  
## ジェネリック関数と型  
 マネージ型であれば、クラス型はジェネリック場合があります。  この例は `List` クラスである可能性があります。  リスト オブジェクトの型は型パラメーターです。  さまざまな種類のオブジェクトの `List` クラスが必要な場合は、ジェネリックは項目の種類として **System::Object** を受け取る `List` を使用したりする前にあります。  ただし、オブジェクト \(間違った型のオブジェクト\) を含むリストで使用できるようになります。  このようなリストは、型指定されていないコレクション クラスと呼ばれます。  状態、実行時に型を確認し、例外をスローすることができます。  または、一度アセンブリにコンパイルした一般的な品質を別のテンプレートを使用することがあります。  アセンブリのコンシューマーは、テンプレートの独自の特殊化を作成できませんでした。  ジェネリック コレクションは、型指定されていないコレクションは、受け入れを意図していない型を配置する場合は、コンパイル エラーが発生するという、二つの`List<double>` \(「リスト」\) と `List<int>` \(「int」など\) のリストとして型指定されたコレクション クラスを作成することができます。  また、これらの型はコンパイル後に一般的に残ります。  
  
 ジェネリック クラスの構文の説明には [Generic Classes \(C\+\+\/CLI\)](../Topic/Generic%20Classes%20\(C++-CLI\).md)`.`A の新しい名前空間、<xref:System.Collections.Generic>である可能性がある一連の <xref:System.Collections.Generic.Dictionary%602>、<xref:System.Collections.Generic.List%601> と <xref:System.Collections.Generic.LinkedList%601>などパラメーター化されたなコレクション型について説明します。  詳細については、「[.NET Framework クラス ライブラリのジェネリック](../Topic/Generics%20in%20the%20.NET%20Framework%20Class%20Library%20\(C%23%20Programming%20Guide\).md)」を参照してください。  
  
 インスタンスおよび静的クラス メンバーの両方の関数、デリゲートとグローバル関数もジェネリック場合があります。  ジェネリック関数は関数のパラメーターが不明な型であるか、関数自体がジェネリック型を使用する必要があります。  多くの場合 **System::Object** が不明なオブジェクト型のパラメーターとして以前使用できる場所のジェネリック型パラメーターはより多くのタイプ セーフなコードに可能性があり、割り当てる代わりに使用されます。  関数が用に設計されており、どの型を渡すと、コンパイル時のエラーとしてフラグが設定されます。  関数のパラメーターとして **System::Object** を使用して、関数が処理することを意図していないオブジェクトの不注意渡すことは、関数本体の特定の種類の不明なオブジェクト型にキャストしなければ、InvalidCastException が発生する可能性を示します。検出されていない。  ジェネリックによって、関数にオブジェクトを渡す場合は、コードでは、型の不一致が発生する正しい型を持つように、関数本体が保証されます。  
  
 同じ利点はジェネリックでビルドされたコレクション クラスに適用されます。  以前コレクション クラスは、コレクションの要素を格納するために **System::Object** を使用します。  コレクションが用に設計されており、型のオブジェクトの挿入がコンパイル時にないオブジェクトが挿入された場合でも、フラグが立てられないします。  通常、別の型のオブジェクトがコレクションにアクセスしたときにキャストされます。  キャストが失敗したときに予期しない型だけが検出されます。  ジェネリックは、コンパイル時に \(または暗黙的な変換へのジェネリック コレクション型パラメーターと一致しない型を挿入するコードを検出し、この問題が解決されます。  
  
 構文の詳細については、「[Generic Functions \(C\+\+\/CLI\)](../windows/generic-functions-cpp-cli.md)」を参照してください。  
  
## ジェネリックと使用される用語  
  
##### 型パラメーター。  
 ジェネリック宣言は *型パラメーター*と呼ばれる一つ以上の不明な型が含まれています。  型パラメーターはジェネリック宣言の本体内の種類を示す名前を付けます。  型パラメーターはジェネリック宣言の本体内の型として使用されます。  ListT\<\> のジェネリック宣言は型パラメーター T.が含まれます。  
  
##### 型の引数  
 *型引数は* ジェネリックで特定のために特化または入力すると、型パラメーターの代わりに使用される実際の型です。  たとえば、`int` は `List<int>`の型引数です。  値型と HANDLE 型はジェネリック型引数として使用される唯一の型です。  
  
##### 構築された型  
 ジェネリック型から構築された型は *構築された型*と呼ばれます。  完全に `List<T>` など、指定されていない型は *オープン構築型*;です 完全に `List<double>,` などの、指定した型と *クローズ構築型* または *特殊な型*です。  オープン構築型は他のジェネリック型またはジェネリック メソッドの定義で使用され、外側のジェネリック自体が指定されるまで完全に指定されていないそうでない場合があります。  たとえば、ジェネリックの基本クラスとしてオープン構築型の使用です:  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### 制約  
 制約は、型パラメーターとして使用できる型の制限です。  たとえば、特定のジェネリック クラスは、指定されたクラスから継承する、または実装します指定したインターフェイスをクラスのみを受け入れることができます。  詳細については、「[Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md)」を参照してください。  
  
## 参照型や値型  
 ハンドルの型と値型では、型引数として使用されることがあります。  いずれかの型が使用される可能性がある一般的な定義では、構文は参照型のインスタンスです。  型パラメーターの型のメンバーにアクセスする場合などに最終的に使用される型が参照型または値型であるかどうか、**\-\>** の演算子が使用されます。  値型が型引数として使用されると、ランタイムは値型をボックス化で直接値型を使用するコードを生成します。  
  
 参照型をジェネリック型引数として使用する場合、Handles 構文を使用します。  値型をジェネリック型引数として使用するときに、型の名前を直接使用します。  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## 型パラメーター。  
 ジェネリック クラスの型パラメーターは、他の識別子として扱われます。  ただし、型がわからないため、使用には制限があります。  たとえば、メンバーを使用できないため、これらのメンバーをサポートすると型パラメーターが認識されている型パラメーターのメソッドが用意されています。  つまり、型パラメーターによってメンバーにアクセスするには、型パラメーターに制約リストにメンバーを含む型を追加する必要があります。  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 この制限は演算子にも使用できます。  制約のないジェネリック型パラメーターは、型がこれらの演算子をサポートする型パラメーターの 2 種類のインスタンスを比較するために `==` と `!=` の演算子を使用できない場合もあります。  これらのチェックは無効なメンバーの使用を確認するには、時間と、ジェネリックの制約を満たすすべてのクラスでランタイムに特化したことがあるため、ジェネリックに、テンプレートに必要です。  
  
 型パラメーターの既定のインスタンスは `()` の演算子を使用して作成できます。  たとえば、次のようになります。  
  
 `T t = T();`  
  
 `T` がジェネリック クラスまたはジェネリック メソッド定義の型パラメーターである場合は、変数を初期化します既定値に。  `T` が ref クラスの場合は、null ポインター。; `T` が値クラスの場合、オブジェクトはゼロに初期化されます。  これは、*既定の初期化子と*呼ばれます。  
  
## 参照  
 [Generics](../windows/generics-cpp-component-extensions.md)