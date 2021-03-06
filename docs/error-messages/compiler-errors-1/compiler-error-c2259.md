---
title: "コンパイラ エラー C2259 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2259
dev_langs: C++
helpviewer_keywords: C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 865eea3ed69ea817aafea011e81033f2bd4ca5f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2259"></a>コンパイラ エラー C2259
'クラス' : 抽象クラスをインスタンス化できません。  
  
 抽象クラスまたは抽象構造体のインスタンスが宣言されています。  
  
 1 つ以上の純粋仮想関数を持つクラスまたは構造体をインスタンス化することはできません。 派生クラスのオブジェクトをインスタンス化するには、派生クラスが各純粋仮想関数をオーバーライドする必要があります。  
  
 詳細については、次を参照してください。[暗黙的な抽象クラス](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes)です。  
  
 次の例では、C2259 が生成されます。  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 インターフェイスから派生して、パブリック以外のアクセス許可を持つインターフェイス メソッドを派生クラスに実装する場合は、常に C2259 が発生する可能性があります。  これは、コンパイラでは、派生クラスに実装されたインターフェイス メソッドはパブリック アクセスを持つことが想定されているために発生します。 より制限の厳しいアクセス許可を持つインターフェイスのメンバー関数を実装する場合、コンパイラはそれらをインターフェイスに定義されるインターフェイス メソッドの実装とは見なさず、代わりにその派生クラスを抽象クラスとします。  
  
 この問題を回避する方法は 2 つあります。  
  
-   実装されるメソッドのアクセス許可をパブリックにします。  
  
-   派生クラスに実装されるインターフェイス メソッドに対してスコープ解決演算子を使用して、実装されるメソッド名をインターフェイスの名前で修飾します。  
  
 C2259 は Visual C 2005 で行った準拠作業の結果として発生する可能性がも**/Zc:wchar_t**が既定でオンでします。 このような状況に c2599 エラーを解決できますか、指定してコンパイル**/Zc:wchar_t-**、以前のバージョン、または可能であればに適合しているため、型を更新することによって動作を取得します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
 次の例では、C2259 が生成されます。  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 次の例では、C2259 が生成されます。  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
