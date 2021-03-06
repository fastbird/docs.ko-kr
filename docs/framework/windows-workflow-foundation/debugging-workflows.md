---
title: "워크플로 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857f227d8541687768f470633e5430aee2171ea8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="debugging-workflows"></a>워크플로 디버깅
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]는 개발 환경에서 실행 중인 워크플로를 디버깅하기 위한 여러 옵션을 제공합니다. 디자이너, XAML 및 코드에서 워크플로를 디버깅할 수 있습니다.  
  
## <a name="debugging-in-the-workflow-designer"></a>워크플로 디자이너에서 디버깅  
 활동을 강조 표시 하 고 키를 눌러 워크플로 디자이너의 활동에 중단점을 설정할 수 있습니다 **F9** 또는 활동의 상황에 맞는 메뉴를 사용 하 여 합니다. 그러면 워크플로 호스트가 디버그 모드에서 실행될 때 워크플로 실행이 중단됩니다. 다음 스크린샷에서는 워크플로 실행이 중단점에서 일시 중지됩니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][워크플로 디자이너로 워크플로 디버깅](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)합니다.  
  
## <a name="debugging-in-xaml"></a>XAML에서 디버깅  
 워크플로가 디자이너의 중단점에서 일시 중지된 경우 XAML에서 워크플로를 디버깅할 수도 있습니다. XAML에서 실행 지점을 보려면 선택 **XAML 뷰의** 워크플로 실행이 일시 중지 될 때 워크플로 디자이너에서 합니다. 솔루션 탐색기에서 디자이너에 워크플로를 다시 열어 디버깅을 다시 디자이너로 전환할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][하는 방법: 워크플로 디자이너로 XAML 디버그](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)합니다.  
  
## <a name="debugging-in-code"></a>코드에서 디버깅  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서는 다른 명령형 응용 프로그램과 동일한 방법으로 코드 중단점을 사용할 수 있습니다. 코드 중단점을 만들려면 코드 창의 왼쪽된 여백을 클릭 하거나 키를 눌러 **F9** 커서 위치에 중단점을 배치 하 합니다.  
  
## <a name="attaching-to-a-workflow-process"></a>워크플로 프로세스에 연결  
 워크플로 디버깅은 Visual Studio 인프라를 사용하여 프로세스에 연결하는 방식도 지원합니다. 이렇게 하면 워크플로 작성자가 Internet Information Services(IIS) 7.0 등 다른 호스트 환경에서 실행되는 워크플로를 디버깅할 수 있습니다.  
  
## <a name="remote-debugging"></a>원격 디버깅  
 [!INCLUDE[wf](../../../includes/wf-md.md)] 원격 디버깅은 다른 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] 구성 요소의 원격 디버깅과 동일하게 작동합니다. 원격 디버깅을 사용 하는 방법은 참조 하십시오. [하는 방법: 원격 디버깅 사용](http://go.microsoft.com/fwlink/?LinkId=196257)합니다.  
  
> [!NOTE]
>  워크플로 응용 프로그램에는 x86 대상으로 하는 경우 아키텍처 고 원격 디버깅을 작동 64 비트 운영 체제를 실행 하는 컴퓨터에서 호스트 될 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] 워크플로 응용 프로그램에서 변경 된 원격 컴퓨터 또는 대상에 설치 되어 **모든 CPU**합니다.  
  
## <a name="extending-the-workflow-debugging-service"></a>워크플로 디버깅 서비스 확장  
 워크플로 디버거 서비스는 현재 공용이며 다시 호스트된 디자이너에서 모니터링, 시뮬레이션 및 디버깅과 같은 사용자 지정 응용 프로그램을 만드는 데 사용될 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] <xref:System.Activities.Presentation.Debug.DebuggerService> 항목을 참조하세요.
