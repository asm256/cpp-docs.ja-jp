---
title: "バイナリ出力ファイル | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8968a47f9d957aa0873b5db78909a6b4ad66ea75
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="binary-output-files"></a>バイナリ出力ファイル
ストリームは本来、テキスト向けとして設計されており、既定の出力モードはテキストです。 テキスト モードでは、改行文字 (16 進数の 10) は、改行 (16 ビットのみ) に展開されます。 この拡大は次のような問題を起こす可能性があります。  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 このプログラムでは、{ 99, 0, 10, 0 } というバイト シーケンスの出力を想定していたところ、{ 99, 0, 13, 10, 0 } が出力されます。バイナリ入力を要求するプログラムで問題が起こります。 文字が変換なしで書き込まれる、本来のバイナリ出力が必要であれば、[ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) コンストラクター オープンモード引数を利用し、バイナリ出力を指定できます。  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ストリーム](../standard-library/output-streams.md)


