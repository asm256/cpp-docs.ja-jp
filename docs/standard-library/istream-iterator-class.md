---
title: "istream_iterator クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::istream_iterator
- iterator/std::istream_iterator::char_type
- iterator/std::istream_iterator::istream_type
- iterator/std::istream_iterator::traits_type
dev_langs: C++
helpviewer_keywords:
- std::istream_iterator [C++]
- std::istream_iterator [C++], char_type
- std::istream_iterator [C++], istream_type
- std::istream_iterator [C++], traits_type
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b5fa9a3636b9aa83344b6ae433afefd2c959d31
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="istreamiterator-class"></a>istream_iterator クラス
入力反復子オブジェクトを表します。 このクラスは、入力ストリームから `Type` クラスのオブジェクトを抽出します。これには、格納している `basic_istream`< `CharType`, `Traits`> への `pointer` 型のオブジェクトを介してアクセスします。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>  
class istream_iterator
 : public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Type`  
 入力ストリームから抽出されるオブジェクトの型。  
  
 `CharType`  
 `istream_iterator` の文字型を表す型。 この引数は省略可能であり、既定値は `char` です。  
  
 `Traits`  
 `istream_iterator` の文字型を表す型。 この引数は省略可能であり、既定値は `char_traits`< `CharType`> です。  
  
 `Distance`  
 `istream_iterator` の相違点の種類を表す符号付き整数型。 この引数は省略可能であり、既定値は `ptrdiff_t` です。  
  
 null 以外の格納されたポインターを使用して istream_iterator クラスのオブジェクトを構築またはインクリメントすると、オブジェクトは、関連付けられている入力ストリームから `Type` 型のオブジェクトを抽出および格納することを試行します。 抽出が失敗した場合、オブジェクトは効果的に格納されたポインターを null ポインターに置き換え、シーケンス終端のインジケーターを作成します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[istream_iterator](#istream_iterator)|既定の `istream_iterator` または読み取り元の反復子のストリーム型に初期化される `istream_iterator` として、ストリームの終わり反復子を構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|`istream_iterator` の文字型を提供する型。|  
|[istream_type](#istream_type)|`istream_iterator` のストリーム型を提供する型。|  
|[traits_type](#traits_type)|`istream_iterator` の文字特性型を提供する型。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator*](#op_star)|逆参照演算子は、`Type` で指定された `istream_iterator` 型の格納されたオブジェクトを返します。|  
|[operator->](#operator-_gt)|メンバーの値 (存在する場合) を返します。|  
|[operator++](#op_add_add)|入力ストリームからインクリメントされたオブジェクトを抽出するか、オブジェクトをインクリメントする前にオブジェクトをコピーして、そのコピーを返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
##  <a name="char_type"></a>  istream_iterator::char_type  
 `istream_iterator` の文字型を提供する型。  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Chartype** のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '2 4 f' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="istream_iterator"></a>  istream_iterator::istream_iterator  
 既定の `istream_iterator` または読み取り元の反復子のストリーム型に初期化される `istream_iterator` として、ストリームの終わり反復子を構築します。  
  
```
istream_iterator();

istream_iterator(istream_type& _Istr);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Istr`  
 `istream_iterator` を初期化するために読み込まれる入力ストリーム。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、null ポインターを使用して入力ストリーム ポインターを初期化し、ストリームの終わり反復子を作成します。 2 番目のコンストラクターは、*&_Istr* を使用して入力ストリーム ポインターを初期化してから、**Type** 型のオブジェクトの抽出と格納を試みます。  
  
 ストリームの終わり反復子は、`istream_iterator` がストリームの終わりに達しているかどうかのテストに使用できます。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_istream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Used in conjunction with copy algorithm  
   // to put elements into a vector read from cin  
   vector<int> vec ( 4 );  
   vector <int>::iterator Iter;  
  
   cout << "Enter 4 integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
   istream_iterator<int> intvecRead ( cin );  
  
   // Default constructor will test equal to end of stream  
   // for delimiting source range of vecor  
   copy ( intvecRead , istream_iterator<int>( ) , vec.begin ( ) );  
   cin.clear ( );  
  
   cout << "vec = ";  
   for ( Iter = vec.begin( ) ; Iter != vec.end( ) ; Iter++ )  
      cout << *Iter << " "; cout << endl;  
}  
```  
  
##  <a name="istream_type"></a>  istream_iterator::istream_type  
 `istream_iterator` のストリーム型を提供する型。  
  
```
typedef basic_istream<CharType, Traits> istream_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、`basic_istream`\< **CharType**, **Traits**> のシノニムです。  
  
### <a name="example"></a>例  
  `istream_type` を宣言して使用する方法の例については、[istream_iterator](#istream_iterator) に関するセクションを参照してください。  
  
##  <a name="op_star"></a>  istream_iterator::operator*  
 逆参照演算子は、`istream_iterator` で指定された **Type** 型の格納されたオブジェクトを返します。  
  
```
const Type& operator*() const;
```  
  
### <a name="return-value"></a>戻り値  
 **Type** 型の格納されているオブジェクト。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_operator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="istream_iterator__operator-_gt"></a>  istream_iterator::operator-&gt;  
 メンバーの値 (存在する場合) を返します。  
  
```
const Type* operator->() const;
```  
  
### <a name="return-value"></a>戻り値  
 メンバーの値 (存在する場合)。  
  
### <a name="remarks"></a>コメント  
 *i* -> は (\* *i*) と同等です。 *m*  
  
 この演算子は、**&\*\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_operator_vm.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
#include <complex>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Enter complex numbers separated by spaces & then\n"  
        << " a character pair ( try example: '(1,2) (3,4) (a,b)' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator< complex<double> > intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<complex<double> > EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading the real part: " << intRead ->real( ) << endl;  
      cout << "Reading the imaginary part: " << intRead ->imag( ) << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="op_add_add"></a>  istream_iterator::operator++  
 入力ストリームからインクリメントされたオブジェクトを抽出するか、オブジェクトをインクリメントする前にオブジェクトをコピーして、そのコピーを返します。  
  
```
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー演算子は、入力ストリームから抽出された **Type** 型のインクリメントされたオブジェクトへの参照を返し、2 番目のメンバー関数が、このオブジェクトのコピーを返します。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_operator_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="traits_type"></a>  istream_iterator::traits_type  
 `istream_iterator` の文字特性型を提供する型。  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Traits** のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '10 20 a' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [input_iterator_tag 構造体](../standard-library/input-iterator-tag-struct.md)   
 [iterator 構造体](../standard-library/iterator-struct.md)   
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



