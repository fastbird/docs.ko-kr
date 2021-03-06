---
title: "방법: EAP 패턴을 작업에 래핑"
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
helpviewer_keywords: tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae9d90c9bb3d0e8d315cbef510cdfe1b54e66da4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>방법: EAP 패턴을 작업에 래핑
다음 예제에서는 <xref:System.Threading.Tasks.TaskCompletionSource%601>를 사용하여 EAP(이벤트 기반 비동기 패턴) 작업의 임의 시퀀스를 하나의 작업으로 노출하는 방법을 보여 줍니다. 또한이 예제에서는 사용 하는 방법을 <xref:System.Threading.CancellationToken> 에 기본 제공 취소 메서드를 호출 하는 <xref:System.Net.WebClient> 개체입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>참고 항목  
 [TPL 및 일반적인 .NET Framework 비동기 프로그래밍](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
