---
title: "ICorProfilerInfo3::GetAppDomainsContainingModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ff9f63fc004d7249b571d980561171464e74b9a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="797ad-102">ICorProfilerInfo3::GetAppDomainsContainingModule 메서드</span><span class="sxs-lookup"><span data-stu-id="797ad-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="797ad-103">지정된 모듈이 로드된 응용 프로그램 도메인의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="797ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="797ad-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="797ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="797ad-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="797ad-106">[in] 로드된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="797ad-107">[in] `appDomainIds` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="797ad-108">[out] 반환된 요소의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="797ad-109">[out] 응용 프로그램 도메인 ID 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="797ad-110">설명</span><span class="sxs-lookup"><span data-stu-id="797ad-110">Remarks</span></span>  
 <span data-ttu-id="797ad-111">메서드는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="797ad-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="797ad-112">Requirements</span></span>  
 <span data-ttu-id="797ad-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="797ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="797ad-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="797ad-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="797ad-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="797ad-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="797ad-116">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="797ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797ad-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="797ad-117">See Also</span></span>  
 [<span data-ttu-id="797ad-118">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="797ad-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="797ad-119">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="797ad-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="797ad-120">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="797ad-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="797ad-121">프로파일링</span><span class="sxs-lookup"><span data-stu-id="797ad-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)