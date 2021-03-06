---
title: "例外 (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs: C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 40d78e9246d0bb682d63ae094f96123dd4b883e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-cc"></a>例外 (C/C++)
2 つの例外コードは、エラーが発生したときに発生する可能性が。  
  
-   **LoadLibrary**エラー  
  
-   **GetProcAddress**エラー  
  
 例外情報を次に示します。  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 スローされた例外コードは、標準的な VcppException (ERROR_SEVERITY_ERROR、ERROR_MOD_NOT_FOUND) と VcppException (ERROR_SEVERITY_ERROR、ERROR_PROC_NOT_FOUND) 値です。 例外へのポインターを渡す、 **DelayLoadInfo** LPDWORD の値を取得できる構造**GetExceptionInformation**で、 [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082)構造体、ExceptionInformation [0] のフィールド。  
  
 さらに、不適切なビットが grAttrs フィールドに設定されている場合、例外が試行がスローされます。 この例外は、すべてを消して致命的です。  
  
 参照してください[構造体と定数定義](../../build/reference/structure-and-constant-definitions.md)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [エラー処理と通知](../../build/reference/error-handling-and-notification.md)