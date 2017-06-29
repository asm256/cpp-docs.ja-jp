---
title: "&lt;chrono&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 68c68070265c8cc7ff4d6c5c070b4e7849d50a91
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 関数
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>duration_cast
 `duration` オブジェクトを指定した型にキャストします。  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>戻り値  
 対象の型に収まる必要のある場合、省略された期間 `duration` を表す `To` 型の `Dur` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `To` が `duration` のインスタンス化の場合、この関数はオーバーロードの解決に関与しません。  
  
##  <a name="time_point_cast"></a>time_point_cast
 [time_point](../standard-library/time-point-class.md) オブジェクトを指定した型にキャストします。  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>戻り値  
 `time_point` 型の継続時間を含む `To` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `To` が [duration](../standard-library/duration-class.md) のインスタンス化ではない限り、この関数はオーバーロードの解決に関与しません。  
  
## <a name="see-also"></a>関連項目  
 [\<chrono>](../standard-library/chrono.md)

