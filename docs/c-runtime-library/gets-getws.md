---
title: "gets、_getws | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getws
- gets
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _getts
- gets
- _getws
dev_langs:
- C++
helpviewer_keywords:
- getws function
- getts function
- _getws function
- lines, getting
- streams, getting lines
- _getts function
- gets function
- standard input, reading from
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
caps.latest.revision: 32
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: dd8739365a4523fe1ecb9aee9931b376edf2b390
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="gets-getws"></a>gets、_getws
`stdin` ストリームから行を取得します。 これらの関数のセキュリティが強化されたバージョンを使用できます。「[gets_s、_getws_s](../c-runtime-library/reference/gets-s-getws-s.md)」をご覧ください。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。 これらの関数のセキュリティを強化したバージョン gets_s および _getws_s は、引き続き使用できます。 これらの代替関数の詳細については、「[gets_s、_getws_s](../c-runtime-library/reference/gets-s-getws-s.md)」をご覧ください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *gets(   
   char *buffer   
);  
wchar_t *_getws(   
   wchar_t *buffer   
);  
template <size_t size>  
char *gets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 入力文字列の格納場所。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合はその引数を返します。 エラーが発生した場合またはファイルの終端に達した場合は、 `NULL` ポインターを返します。 どちらが発生したかを確認するには、[ferror](../c-runtime-library/reference/ferror.md) または [feof](../c-runtime-library/reference/feof.md) を使用します。 `buffer` が `NULL` の場合は、「[Parameter Validation](../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `NULL` を返し、errno を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `gets` 関数は、`stdin` 標準入力ストリームから行を読み取り、`buffer` に格納します。 行は、最初の改行文字 ('\n') までのすべての文字 (改行文字を含む) で構成されます。 `gets` は、行を返す前に、改行文字を null 文字 ('\0') に置き換えます。 これとは対照的に、`fgets` 関数は改行文字を保持します。 ワイド文字を扱う場合は、`_getws` ではなく `gets` を使用します。引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  
  
> [!IMPORTANT]
>  gets で読み取る文字の数を制限する方法がないため、信頼できない入力によってバッファー オーバーランが発生しやすくなります。 代わりに、 `fgets` を使用してください。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_getts`|`gets`|`gets`|`_getws`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`gets`|\<stdio.h>|  
|`_getws`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_gets.c  
// compile with: /WX /W3  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C4996  
   // Danger: No way to limit input to 20 chars.  
   // Consider using gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
 入力が 20 文字を超えると、行バッファーのオーバーランが発生し、ほぼ確実にプログラムがクラッシュします。  
  
```Output  
  
Hello there!The line entered was: Hello there!  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [fgets、fgetws](../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs、fputws](../c-runtime-library/reference/fputs-fputws.md)   
 [puts、_putws](../c-runtime-library/reference/puts-putws.md)