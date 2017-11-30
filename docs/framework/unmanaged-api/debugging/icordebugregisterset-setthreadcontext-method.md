---
title: "ICorDebugRegisterSet::SetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a97706e5cf407f16b6d06efce11576fbb131d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="2dcf8-102">ICorDebugRegisterSet::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="2dcf8-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="2dcf8-103">`SetThreadContext`.NET Framework 버전 2.0에서에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcf8-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2dcf8-104">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2dcf8-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dcf8-105">상위 수준 작업을 사용 하 여 [icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) 스레드 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcf8-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dcf8-106">구문</span><span class="sxs-lookup"><span data-stu-id="2dcf8-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2dcf8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dcf8-107">Requirements</span></span>  
 <span data-ttu-id="2dcf8-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcf8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dcf8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dcf8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dcf8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dcf8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dcf8-111">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2dcf8-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcf8-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dcf8-112">See Also</span></span>  
 [<span data-ttu-id="2dcf8-113">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dcf8-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="2dcf8-114">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dcf8-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)