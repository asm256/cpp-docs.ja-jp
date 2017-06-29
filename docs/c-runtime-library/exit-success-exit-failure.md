---
title: "EXIT_SUCCESS、EXIT_FAILURE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
dev_langs:
- C++
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 5ef06210cc02a1658b59885f056e1962c1b09a35
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="exitsuccess-exitfailure"></a>EXIT_SUCCESS、EXIT_FAILURE
## <a name="syntax"></a>構文  
  
```  
  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらは **exit** 関数と `_exit` 関数の引数であり、`atexit` 関数と `_onexit` 関数の戻り値です。  
  
## <a name="see-also"></a>関連項目  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)