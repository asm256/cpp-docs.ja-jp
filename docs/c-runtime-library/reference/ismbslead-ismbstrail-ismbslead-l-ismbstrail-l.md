---
title: "_ismbslead、_ismbstrail、_ismbslead_l、_ismbstrail_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
dev_langs:
- C++
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
caps.latest.revision: 22
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
ms.openlocfilehash: 5c74c39a90896f9c04bfc945b420238795b11b74
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="ismbslead-ismbstrail-ismbsleadl-ismbstraill"></a>_ismbslead、_ismbstrail、_ismbslead_l、_ismbstrail_l
マルチバイト文字の文字列の先頭バイトと末尾バイトについて状況依存のテストを実行し、指定された部分文字列のポインターが先頭バイトまたは末尾バイトを指しているかどうかを判断します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbslead(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbstrail(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbslead_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
int _ismbstrail_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の先頭、または直前の既知の先頭バイトを指すポインター。  
  
 `current`  
 テストする、文字列内の位置を指すポインター。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_ismbslead`文字が先頭バイトである場合は-1 を返しますと`_ismbstrail`文字が後続バイトである場合は-1 を返します。 入力文字列が有効であるものの、その文字が先頭バイトでも末尾バイトでもない場合、これらの関数は 0 を返します。 どちらかの引数が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_ismbslead` と `_ismbstrail` は、文字列のコンテキストを考慮に入れるため、`_ismbblead` と `_ismbbtrail` のバージョンより低速です。  
  
 これらの関数の `_l` サフィックスが付いたバージョンは、ロケールに依存する動作について現在のロケールではなく渡されたロケールを使用する点を除いて、同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_ismbslead`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
|`_ismbstrail`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
|`_ismbslead_l`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
|`_ismbstrail_l`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
  
 \* テスト条件のマニフェスト定数の場合。  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
