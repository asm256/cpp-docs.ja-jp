---
title: "コンパイラ エラー C3710 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3710
dev_langs: C++
helpviewer_keywords: C3710
ms.assetid: 18bec009-5b6f-464a-a21e-5d58a6936504
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc39cd77bc9316024d0980be3a432e332f09cbb7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3710"></a>コンパイラ エラー C3710
'function': _ _hook のイベント ハンドラーを指定するための構文が正しくありません/\__unhook  
  
 イベント ハンドラーを指定すると[_ _hook](../../cpp/hook.md)または[_ _unhook](../../cpp/unhook.md)ハンドラーが有効なメソッドにする必要があります。  
  
## <a name="example"></a>例  
 次のサンプルの生成 C3710  
  
```  
// C3710.cpp  
// compile with: /link /opt:noref  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
#include <stdio.h>  
  
[event_source(native)]  
class CEventSrc  
{  
public:  
    __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec  
{  
public:  
    void handler1()  
    {  
        printf_s("Executing handler1().\n");  
    }  
  
    void HookEvents(CEventSrc* pSrc)   
    {  
        __hook(&CEventSrc::event1, pSrc, 0);   // C3710  
        // try the following line instead  
        // __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);  
    }  
  
    void UnhookEvents(CEventSrc* pSrc)  
    {  
        __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);  
    }  
};  
  
int main()  
{  
    CEventSrc eventSrc;  
    CEventRec eventRec;  
    eventRec.HookEvents(&eventSrc);  
    eventSrc.event1();  
    eventRec.UnhookEvents(&eventSrc);  
}  
```