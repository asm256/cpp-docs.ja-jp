---
title: "テキスト モードとバイナリ モードの Unicode ストリーム入出力 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.io
dev_langs: C++
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df81013b497c0be939ceb3afd44d8a3e9e28ce18
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>テキスト モードとバイナリ モードの Unicode ストリーム入出力
Unicode ストリームの入出力ルーチン (`fwprintf`、`fwscanf`、`fgetwc`、`fputwc`、`fgetws`、または `fputws` など) がテキスト モード (既定) で開かれたファイルを操作すると、次の 2 種類の文字変換が行われます。  
  
-   Unicode からマルチバイト文字セット (MBCS: Multibyte Character Set) への変換、または MBCS から Unicode への変換。 Unicode ストリーム入出力関数をテキスト モードで実行すると、入力ストリームまたは出力ストリームはマルチバイト文字のシーケンスであると想定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、`mbtowc` 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 `wctomb` 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。  
  
-   キャリッジ リターンとラインフィード (CR-LF: Carriage return - linefeed) の変換。 CR-LF 変換は、MBCS から Unicode への変換の前 (Unicode ストリーム入力関数の場合) と Unicode から MBCS への変換の後 (Unicode ストリーム出力関数の場合) に行われます。 入力時には、それぞれの CR-LF シーケンスが 1 つのラインフィード文字に変換されます。 出力時には、それぞれのラインフィード文字が CR-LF シーケンスに変換されます。  
  
 ただし、Unicode ストリーム入出力関数をバイナリ モードで実行すると、ファイルが Unicode であると想定されるため、入出力時に CR-LF 変換も文字変換も行われません。 Unicode テキスト ファイルで wcin オブジェクトを正しく使用するための命令 _setmode( _fileno( stdin ), _O_BINARY ) を使用してください。  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [入出力](../c-runtime-library/input-and-output.md)