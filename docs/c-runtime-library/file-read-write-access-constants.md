---
title: "ファイル読み出し/書き込みアクセス定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.constants.file
dev_langs: C++
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d32e9da99776bf5e21805ec239c2731cc3d5f21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="file-readwrite-access-constants"></a>ファイル読み出し/書き込みアクセス定数
## <a name="syntax"></a>構文  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらの定数は、ファイルに対して要求されるアクセスの種類 ("a"、"r"、または "w") を指定します。 [変換モード](../c-runtime-library/file-translation-constants.md) ("b" または "t") と[ディスク コミット モード](../c-runtime-library/commit-to-disk-constants.md) ("c" または "n") をアクセスの種類で指定できます。  
  
 アクセスの種類は次のとおりです。  
  
 **"a"**  
 ファイルの末尾への書き込み用にファイルを開きます (追加モード)。ファイルが存在しない場合は、まず、ファイルを作成します。 すべての書き込み操作はファイルの終端で行われます。 `fseek` または **rewind** を使用することでファイル ポインターの位置を変更できますが、書き込み操作は常にファイル ポインターをファイルの終端に戻した後に実行されます。  
  
 **"a+"**  
 上記と同様ですが、読み取りも許可されます。  
  
 **"r"**  
 読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、ファイルを開く呼び出しは失敗します。  
  
 **"r+"**  
 読み取りと書き込みの両方のモードで開きます。 ファイルが存在しない場合や見つからない場合、ファイルを開く呼び出しは失敗します。  
  
 **"w"**  
 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 **"w+"**  
 読み取りと書き込みの両方のモードで空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 "r+"、"w+"、または "a+" のいずれかを指定すると、読み取りと書き込みの両方を行うことができます (この場合、ファイルは"更新"用に開かれると言います)。 ただし、読み取りと書き込みを切り替える場合は、その前に `fflush`、`fsetpos`、`fseek`、または **rewind** のいずれかの操作を実行する必要があります。 `fsetpos` または `fseek` の操作には現在位置を指定できます。  
  
## <a name="see-also"></a>関連項目  
 [_fdopen、_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_popen、_wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)