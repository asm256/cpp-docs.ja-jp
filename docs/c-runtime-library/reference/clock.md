---
title: clock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clock
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3a226377499df1747a022325b762b3cdfdd35ea6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="clock"></a>clock
呼び出しプロセスにかかったウォール クロック時間を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>戻り値  
プロセスの開始時の CRT の初期化からの経過時間 (`CLOCKS_PER_SEC` 単位/秒で計測)。 経過時間を計測できない場合や、`clock_t` 型として記録できる正の最大期間を超えた場合、関数は値 `(clock_t)(-1)` を返します。   
  
## <a name="remarks"></a>コメント  
`clock` 関数は、プロセス開始時の CRT の初期化から経過したウォール クロック時間を示します。 この関数は、厳密には ISO C (正味の CPU 時間を戻り値にすることが規定されている) に準拠していないことに注意してください。 CPU 時間を取得するには、Win32 の [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) 関数を使用します。 秒単位で経過時間を求めるには、`clock` 関数によって返された値をマクロ `CLOCKS_PER_SEC` で除算します。  
  
十分な時間がある場合、`clock` から返される値は `clock_t` の正の最大値を超える可能性があります。 プロセスの実行時間が長い場合、`clock` から返される値は常に `(clock_t)(-1)` となります。これは、ISO C99 (7.23.2.1) と ISO C11 標準 (7.27.2.1) で指定されています。 Microsoft では `clock_t` を `long` (符号付き 32 ビット整数) として実装しており、`CLOCKS_PER_SEC` マクロは 1000 として定義されています。 これで、`clock` 関数の最大戻り値は 2147483.647 秒 (約 24.8 日) となります。 この時間より長く実行されるプロセスでは、`clock` から返される値を信頼しないでください。 64 ビットの `time` 関数または Windows の [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) 関数を使用して、プロセスの数年の経過時間を記録することができます。  

## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`clock`|\<time.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_clock.c  
// This sample uses clock() to 'sleep' for three 
// seconds, then determines how long it takes  
// to execute an empty loop 600000000 times.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
// Pauses for a specified number of milliseconds.  
void do_sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
  
const long num_loops = 600000000L;

int main( void )  
{  
   long    i = num_loops;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "Time to do %ld empty loops is ", num_loops );  
   printf( "%2.3f seconds\n", duration );  
}  
```  
  
```Output  
Delay for three seconds  
Done!  
Time to do 600000000 empty loops is 1.354 seconds  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [difftime、_difftime32、_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)
