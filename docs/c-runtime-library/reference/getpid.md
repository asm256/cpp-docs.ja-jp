---
title: _getpid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _getpid
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords: _getpid
dev_langs: C++
helpviewer_keywords:
- getpid function
- _getpid function
- process identification numbers
ms.assetid: d3e13bae-9a0c-4f33-86d3-ec9df9519285
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3a0405eab9210348b1b9ffcd20e21a731a23606d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="getpid"></a>_getpid
プロセス ID を取得します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「                  [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int _getpid( void );  
```  
  
## <a name="return-value"></a>戻り値  
 システムから取得したプロセス ID を返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_getpid` 関数は、システムからプロセス ID を取得します。 プロセス ID は、呼び出し元プロセスを一意に識別します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_getpid`|\<process.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_getpid.c  
// This program uses _getpid to obtain  
// the process ID and then prints the ID.  
  
#include <stdio.h>  
#include <process.h>  
  
int main( void )  
{  
   // If run from command line, shows different ID for   
   // command line than for operating system shell.  
  
   printf( "Process id: %d\n", _getpid() );  
}  
```  
  
```Output  
Process id: 3584  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_mktemp、_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)