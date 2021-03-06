---
title: "방법: 낮은 수준의 동기화에 SpinLock 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>방법: 낮은 수준의 동기화에 SpinLock 사용
다음 예제에서는 사용 하는 <xref:System.Threading.SpinLock>합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 임계 영역 수행 작업에 대 한 적절 한 후를 하므로 양이 최소 이며는 <xref:System.Threading.SpinLock>합니다. 약간 증가 하는 작업의 성능이 향상 된 <xref:System.Threading.SpinLock> 표준 잠금에 비교 합니다. 그러나 SpinLock이 표준 잠금보다 비용이 드는 지점이 있습니다. 프로파일링 도구에서 동시성 프로파일링 기능을 사용하여 어떤 유형의 잠금이 프로그램에서 더 나은 성능을 제공하는지 확인할 수 있습니다. 자세한 내용은 [동시성 시각화 도우미](/visualstudio/profiling/concurrency-visualizer)를 참조하세요.  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>공유 리소스에 대 한 잠금을 유지로 이동 하지 않는 경우에 유용할 수 있습니다 매우 긴 합니다. 이러한 경우에 다중 코어 컴퓨터에서 차단된 스레드를 잠금이 해제될 때까지 몇 차례 회전하는 것이 효율적입니다. CPU를 많이 사용하는 프로세스이기 때문에 회전함으로써 스레드가 차단되지 않습니다. <xref:System.Threading.SpinLock>회전 논리 프로세서 수 또는 하이퍼 스레딩이 있는 시스템에서 우선 순위 반전 기아 상태 방지 하기 위해 특정 조건에서 중지 됩니다.  
  
 사용 하 여이 예제는 <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> 다중 스레드 액세스에 대 한 사용자 동기화를 필요로 하는 클래스입니다. 다른 옵션은.NET Framework 버전 4 대상으로 하는 응용 프로그램에서 사용 하는 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, 모든 사용자 잠금이 필요가 없습니다.  
  
 사용 하 여 `false` (`False` Visual basic에서)에 대 한 호출에서 <xref:System.Threading.SpinLock.Exit%2A>합니다. 그러면 최상의 성능을 제공합니다. IA64 아키텍처에서 `true`(`True`)을 지정하여 메모리 담장을 사용합니다. 그러면 쓰기 버퍼를 플러시하여 종료할 다른 스레드에서 잠금을 사용할 수 있는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
