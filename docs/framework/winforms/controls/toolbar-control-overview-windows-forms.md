---
title: "ToolBar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857cc04af6c619035fa2bf0a548053f57292f7bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="toolbar-control-overview-windows-forms"></a>ToolBar 컨트롤 개요(Windows Forms)
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ToolBar> 컨트롤은 폼에서 드롭다운 메뉴 및 명령을 활성화하는 비트맵 단추가 포함된 한 행을 표시하는 컨트롤 막대로 사용됩니다. 따라서 도구 모음 단추를 클릭하는 것은 메뉴 명령을 선택하는 것과 같을 수 있습니다. 단추는 누름 단추, 드롭다운 메뉴 또는 구분 기호로 표시 되고 동작하도록 구성할 수 있습니다. 일반적으로 도구 모음에는 응용 프로그램 메뉴 구조의 항목에 해당하는 단추 및 메뉴가 포함되며, 응용 프로그램에서 자주 사용되는 함수 및 명령에 대한 빠른 액세스를 제공합니다.  
  
## <a name="working-with-the-toolbar-control"></a>ToolBar 컨트롤 사용  
 A <xref:System.Windows.Forms.ToolBar> 도킹 컨트롤은 일반적으로 "고정" 위쪽 해당 부모 창에 있지만 창의 모든 면에 도킹 될 수도 있습니다. 도구 모음에서 사용자가 마우스 포인터로 도구 모음 단추를 가리키면 도구 설명을 표시할 수 있습니다. 도구 설명은 단추 또는 메뉴의 기능을 간략하게 설명하는 작은 팝업 창입니다. 도구 설명을 표시 하는 <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> 속성으로 설정 되어 있어야 `true`합니다.  
  
> [!NOTE]
>  특정 응용 프로그램은 응용 프로그램 창 위에서 "고정 해제"되어 위치를 변경할 수 있는 도구 모음과 매우 비슷한 기능이 있는 컨트롤을 제공합니다. Windows Forms ToolBar 컨트롤은 이러한 동작을 수행할 수 없습니다.  
  
 경우는 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 속성이 <xref:System.Windows.Forms.ToolBarAppearance>, 도구 모음 단추 볼록하게 표시 합니다. 설정할 수 있습니다는 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 도구 모음의 속성 <xref:System.Windows.Forms.ToolBarAppearance> 평면 모양 도구 모음 및 단추를 제공 합니다. 마우스 포인터를 평면 모양의 단추 위로 움직이면 단추 모양이 3차원 모양으로 바뀝니다. 도구 모음 단추는 구분 기호를 사용하여 논리 그룹으로 나눌 수 있습니다. 구분 기호는 도구 모음 단추는 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성이로 설정 <xref:System.Windows.Forms.ToolBarButtonStyle>합니다. 도구 모음에서 빈 공간으로 나타납니다. 도구 모음이 평면 모양이면 단추 구분 기호는 단추 사이의 공간이 아니라 선으로 나타납니다.  
  
 <xref:System.Windows.Forms.ToolBar> 컨트롤 도구 모음을 추가 하 여 만들 수 있습니다 <xref:System.Windows.Forms.Button> 개체는 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 컬렉션입니다. 컬렉션 편집기를 사용 하 여 단추를 추가 하는 <xref:System.Windows.Forms.ToolBar> ; 각 <xref:System.Windows.Forms.Button> 둘 다에 할당할 수 있지만 개체는 텍스트 또는 이미지가 지정에 있어야 합니다. 이미지는 연결된 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 구성 요소에서 제공됩니다. 실행 시 추가 하거나에서 단추를 제거할 수 있습니다는 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> 를 사용 하는 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> 및 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> 메서드. 단추를 프로그래밍 하는 <xref:System.Windows.Forms.ToolBar>, 코드를 추가 하는 <xref:System.Windows.Forms.ToolBar.ButtonClick> 의 이벤트는 <xref:System.Windows.Forms.ToolBar>를 사용 하 여는 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> 속성의는 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 어떤 단추가 클릭 되었는지 확인 하려면 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolBar>  
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [방법: ToolBar 컨트롤에 단추 추가](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 [방법: ToolBar 단추의 아이콘 정의](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [방법: Toolbar 단추의 메뉴 이벤트 트리거](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)
