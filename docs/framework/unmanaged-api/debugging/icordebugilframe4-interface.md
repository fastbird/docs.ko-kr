---
title: "ICorDebugILFrame4 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a>ICorDebugILFrame4 인터페이스
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 IL(중간 언어) 코드의 스택 프레임에서 로컬 변수 및 코드에 액세스하는 데 사용할 수 있는 메서드를 제공합니다. 디버거가 프로파일러 ReJIT 계측에 추가된 변수와 코드에 액세스할 수 있는지는 매개 변수를 통해 지정됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateLocalVariablesEx 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|현재 프레임에서 사용할 수 있는 로컬 변수 목록을 반환합니다.|  
|[GetCodeEx 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|이 스택 프레임에서 실행 중인 코드를 반환합니다.|  
|[GetLocalVariableEx 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|IL 프레임의 로컬 변수 값을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 이외에서 제공 하는 기능을 제공 하는 이러한 메서드는 [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), 및 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 메서드. 각 메서드는 프로파일러 ReJIT 요청에 의해 정의된 추가 로컬 변수나 코드가 표시되는지 여부를 지정하는 `flags` 매개 변수를 포함합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
