---
title: _write | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _write
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
apitype: DLLExport
f1_keywords:
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
caps.latest.revision: 21
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9e6e654e043a71cbb6eb75c53077b14400b82d72
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="write"></a>_write
ファイルにデータを書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
int _write(  
   int fd,  
   const void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 データを書き込むファイルのファイル記述子。  
  
 `buffer`  
 書き込むデータ。  
  
 `count`  
 バイト数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、`_write` は実際に書き込まれたバイト数を返します。 ディスク上に残っている実際の領域が、この関数がディスクに書き込もうとしているバッファーのサイズよりも小さい場合、`_write` は失敗し、バッファーの内容はディスクにフラッシュされません。 戻り値-1 はエラーを示します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は -1 を返し、`errno` は次の 3 つの値のいずれかに設定されます。`EBADF` は、ファイル記述子が無効であるか、ファイルが書き込み用に開かれていないことを意味します。`ENOSPC` は、操作対象のデバイス上に十分な領域が残っていないことを意味します。`EINVAL` は、`buffer` が null ポインターであったか、Unicode モードで奇数の `count` のバイトがファイルに書き込むために渡されたことを意味します。  
  
 これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 ファイルがテキスト モードで開かれている場合、各ライン フィード文字は、キャリッジ リターンの出力に改行をペアに置き換えられます。 この置き換えは、戻り値には影響しません。  
  
 ファイルが Unicode 変換モードで開かれた場合 (たとえば、`_open` または `_sopen` と、`_O_WTEXT`、`_O_U16TEXT`、または `_O_U8TEXT` を含むモード パラメーターを使用することで `fd` が開かれた場合や、`fopen` と `ccs=UNICODE`、`ccs=UTF-16LE`、または `ccs=UTF-8` を含むモード パラメーターを使用して開かれた場合や、`_setmode` を使用してモードが Unicode 変換モードに変更された場合など)、`buffer` は **UTF-16** データを含む `wchar_t` の配列へのポインターとして解釈されます。 このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 `_write` 関数は、`count` のバイトを `buffer` から `fd` に関連付けられたファイルにコピーします。 書き込み操作は、指定されたファイルに関連付けられたファイル ポインター (存在する場合) の現在の位置で開始されます。 ファイルが追加用に開かれている場合、操作はファイルの現在の末尾で開始されます。 書き込み操作の後、ファイル ポインターは実際に書き込まれたバイト数の分、増加します。  
  
 ファイルへの書き込みがテキスト モードで開かれた場合、`_write` は CTRL+Z 文字を論理的なファイルの終わりとして扱います。 デバイスに書き込むときに、`_write` はバッファー内の CTRL+Z 文字を出力の終端として扱います。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_write`|\<io.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt__write.c  
//   
// This program opens a file for output and uses _write to write  
// some bytes to the file.  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <errno.h>  
#include <share.h>  
  
char buffer[] = "This is a test of '_write' function";  
  
int main( void )  
{  
   int         fileHandle = 0;  
   unsigned    bytesWritten = 0;  
  
   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,  
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )  
      return -1;  
  
   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )  
   {  
      switch(errno)  
      {  
         case EBADF:  
            perror("Bad file descriptor!");  
            break;  
         case ENOSPC:  
            perror("No space left on device!");  
            break;  
         case EINVAL:  
            perror("Invalid parameter: buffer was NULL!");  
            break;  
         default:  
            // An unrelated error occured   
            perror("Unexpected error!");  
      }  
   }  
   else  
   {  
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );  
   }  
   _close( fileHandle );  
}  
```  
  
```Output  
Wrote 36 bytes to file.  
```  
  
## <a name="see-also"></a>関連項目  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
