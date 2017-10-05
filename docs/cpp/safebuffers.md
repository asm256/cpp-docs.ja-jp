---
title: "safebuffers |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- safebuffers
- safebuffers_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ceb7d5796002bd54055b74d56a136706890494c4
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="safebuffers"></a>safebuffers
**Microsoft 固有の仕様**  
  
 関数のバッファー オーバーラン セキュリティ チェックを挿入しないようにコンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>コメント  
 **/GS**コンパイラ オプションは、スタック上のセキュリティ チェックを挿入することによってバッファー オーバーランをテストするコンパイラです。 セキュリティ チェックの対象になるデータ構造の種類は「 [/GS (バッファー セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)です。 バッファー オーバーランの検出の詳細については、次を参照してください。[コンパイラ セキュリティ チェックで深さ](http://go.microsoft.com/fwlink/?linkid=7260)MSDN Web サイトです。  
  
 専門家による手動コード レビューまたは外部解析によって、関数がバッファー オーバーランしないと判断される場合もあります。 その場合は、適用することで、関数のセキュリティ チェックを抑制できます、`__declspec(safebuffers)`関数の宣言キーワード。  
  
> [!CAUTION]
>  バッファー セキュリティ チェックは重要なセキュリティ保護を提供し、パフォーマンスにはほとんど影響がありません。 したがって、関数のパフォーマンスが重視され、関数が安全であることが判明しているまれなケースを除き、チェックを抑制しないことをお勧めします。  
  
## <a name="inline-functions"></a>インライン関数  
 A*プライマリ関数*使用できる、[インライン展開](inline-functions-cpp.md)のコピーを挿入するキーワード、*セカンダリ関数*です。 場合、`__declspec(safebuffers)`キーワードが関数に適用される、その関数のバッファー オーバーランの検出を抑制します。 ただし、インライン展開に影響、`__declspec(safebuffers)`キーワードを次のようにします。  
  
 たとえば、 **/GS**どちらの関数のコンパイラ オプションが指定されましたが、主な機能を指定します、`__declspec(safebuffers)`キーワード。 セカンダリ関数のデータ構造によってセキュリティ チェックの対象となり、関数はこれらのチェックを抑制しません。 この場合、次のようになります。  
  
-   指定して、 [_ _forceinline](inline-functions-cpp.md)コンパイラの最適化に関係なく関数のインライン展開を強制的にセカンダリ関数ではキーワードです。  
  
-   セカンダリ関数はセキュリティ チェックの対象となるため、セキュリティ チェックにも適用されます、主な機能を指定しても、`__declspec(safebuffers)`キーワード。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、`__declspec(safebuffers)`キーワード。  
  
```  
// compile with: /c /GS  
typedef struct {  
    int x[20];  
} BUFFER;  
static int checkBuffers() {  
    BUFFER cb;  
    // Use the buffer...  
    return 0;  
};  
static __declspec(safebuffers)   
    int noCheckBuffers() {  
    BUFFER ncb;  
    // Use the buffer...  
    return 0;  
}  
int wmain() {  
    checkBuffers();  
    noCheckBuffers();  
    return 0;  
}  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [inline、_ _inline、 \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)