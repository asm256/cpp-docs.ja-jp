---
title: "fseek 定数と _lseek 定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
dev_langs: C++
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 714a25838c40286fac69fafb88d673e65b1e2f14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fseek-lseek-constants"></a>fseek 定数と _lseek 定数
## <a name="syntax"></a>構文  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 *origin* 引数は初期位置を指定し、次のマニフェスト定数のいずれかになります。  
  
|定数|説明|  
|--------------|-------------|  
|`SEEK_END`|ファイルの終端|  
|`SEEK_CUR`|ファイル ポインターの現在の位置|  
|`SEEK_SET`|ファイルの先頭|  
  
## <a name="see-also"></a>関連項目  
 [fseek、_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek、_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)