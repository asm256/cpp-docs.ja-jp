---
title: "memcmp、wmemcmp | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcmp
- wmemcmp
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memcmp
- wmemcmp
dev_langs:
- C++
helpviewer_keywords:
- wmemcmp function
- memcmp function
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
caps.latest.revision: 14
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: af4d8eab26873d9c29ab8343afc462e7ed22060c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/28/2017

---
# <a name="memcmp-wmemcmp"></a>memcmp、wmemcmp
2 つのバッファーの文字を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
int memcmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count  
);  
int wmemcmp(  
   const wchar_t * buf1,  
   const wchar_t * buf2,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buf1`  
 最初のバッファー。  
  
 `buf2`  
 2 番目のバッファー。  
  
 `count`  
 比較する文字数 (`memcmp` の場合はバイト数、`wmemcmp` の場合はワイド文字数を比較します)。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、バッファー間の関係を示しています。  
  
|戻り値|buf1 と buf2 の最初の `count` 文字数の関係|  
|------------------|---------------------------------------------------------------|  
|< 0|`buf1` が `buf2` より小さい|  
|0|`buf1` が `buf2` と同じ|  
|> 0|`buf1` が `buf2` より大きい|  
  
## <a name="remarks"></a>コメント  
 `count` と `buf1` の最初の `buf2` 文字数を比較します。 ゼロ以外の戻り値の符号は、バッファー間で最初に異なる値のペアの差の符号です。 値は、`unsigned char` の場合は `memcmp` として解釈され、`wchar_t` の場合は `wmemcmp` として解釈されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`memcmp`|\<memory.h> または \<string.h>|  
|`wmemcmp`|\<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```C  
// crt_memcmp.c  
/* This program uses memcmp to compare  
 * the strings named first and second. If the first  
 * 19 bytes of the strings are equal, the program  
 * considers the strings to be equal.  
 */  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char first[]  = "12345678901234567890";  
   char second[] = "12345678901234567891";  
   int int_arr1[] = {1,2,3,4};  
   int int_arr2[] = {1,2,3,4};  
   int result;  
  
   printf( "Compare '%.19s' to '%.19s':\n", first, second );  
   result = memcmp( first, second, 19 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else  
      printf( "First is greater than second.\n" );  
  
   printf( "Compare '%d,%d' to '%d,%d':\n", int_arr1[0], int_arr1[1], int_arr2[0], int_arr2[1]);  
   result = memcmp( int_arr1, int_arr2, sizeof(int) * 2 );  
   if( result < 0 )  
      printf( "int_arr1 is less than int_arr2.\n" );  
   else if( result == 0 )  
      printf( "int_arr1 is equal to int_arr2.\n" );  
   else   
      printf( "int_arr1 is greater than int_arr2.\n" );  
}  
```  
  
```Output  
Compare '1234567890123456789' to '1234567890123456789':  
First is equal to second.  
Compare '1,2' to '1,2':  
int_arr1 is equal to int_arr2.  
```  
  
## <a name="see-also"></a>関連項目  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)
