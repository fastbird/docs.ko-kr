---
title: "NukeDownloadedCache 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache 함수
공용 언어 런타임 (CLR) 다운로드 캐시를 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 CLR 다운로드 캐시는 다시 사용할 수 있도록 URL에서 다운로드 하는 강력한 이름의 어셈블리를 저장 하는 영역입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다. 올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CreateHistoryReader 함수](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [GetHistoryFileDirectory 함수](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
