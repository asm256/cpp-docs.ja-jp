---
title: imaxdiv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: imaxdiv
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: imaxdiv
dev_langs: C++
helpviewer_keywords: imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65c7b71030bff65a2806d20690554a9828871268
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="imaxdiv"></a>imaxdiv
任意のサイズの 2 つの整数値の商および剰余を単一の操作として計算します。  
  
## <a name="syntax"></a>構文  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### <a name="parameters"></a>パラメーター  
 `numer`  
 分子。  
  
 `denom`  
 分母。  
  
## <a name="return-value"></a>戻り値  
 `imaxdiv` を [intmax_t](../../c-runtime-library/standard-types.md) 型の引数を使用して呼び出した場合、商と剰余で構成される [imaxdiv_t](../../c-runtime-library/standard-types.md) 型の構造体を返します。  
  
## <a name="remarks"></a>コメント  
 `imaxdiv` 関数は `numer` を `denom` で割り、商と剰余を計算します。 `imaxdiv_t` 構造体には、商 `intmax_t quot` と剰余 `intmax_t rem` が含まれます。 商の符号は、数学的な商の符号と同じです。 この絶対値が最も大きい整数であり、商の絶対値よりも小さくなります。 分母が 0 の場合、プログラムはエラー メッセージにより終了します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`imaxdiv`|\<inttypes.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 このコードをビルドしてからコマンド ライン パラメーターで `9460730470000000 8766` を指定した呼び出した場合、次の出力が生成されます。  
  
```Output  
The call to imaxdiv(9460730470000000, 8766)  
results in a quotient of 1079252848505, and a remainder of 5170  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv、lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)