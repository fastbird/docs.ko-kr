---
title: ".NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89be7e347556c8ec34296044f17fbfd4450bc127
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a>.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발
Windows Forms 컨트롤은 사용자 인터페이스 기능을 캡슐화하고 클라이언트 측 Windows 기반 응용 프로그램에서 사용되는 재사용 가능한 구성 요소입니다. Windows Forms은 바로 사용할 수 있는 많은 컨트롤을 제공할 뿐만 아니라 고유한 컨트롤을 개발하기 위한 인프라도 제공합니다. 기존 컨트롤을 결합 또는 확장하거나 고유한 사용자 지정 컨트롤을 작성할 수 있습니다. 이 섹션에서는 Windows Forms 컨트롤을 개발하는 데 도움이 되는 배경 정보 및 샘플을 제공합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Windows Forms에서 컨트롤 사용 개요](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)  
 Windows Forms 응용 프로그램에 있는 컨트롤 사용의 필수 요소를 요약해서 설명합니다.  
  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스로 작성할 수 있는 다양한 종류의 사용자 지정 컨트롤을 설명합니다.  
  
 [Windows Forms 컨트롤 개발 기본 사항](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 Windows Forms 컨트롤 개발의 첫 번째 단계를 설명합니다.  
  
 [Windows Forms 컨트롤의 속성](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 Windows Forms 컨트롤에 속성을 추가하는 방법을 보여 줍니다.  
  
 [Windows Forms 컨트롤의 이벤트](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 Windows Forms 컨트롤에서 이벤트를 처리 및 정의하는 방법을 보여 줍니다.  
  
 [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.  
  
 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 컨트롤의 모양을 사용자 지정하는 방법을 보여 줍니다.  
  
 [Windows Forms 컨트롤의 레이아웃](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)  
 컨트롤 및 폼에 사용할 정교한 레이아웃을 만드는 방법을 보여 줍니다.  
  
 [Windows Forms 컨트롤의 다중 스레딩](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)  
 다중 스레드 컨트롤을 구현하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [구성 요소의 디자인 타임 특성](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 비주얼 디자이너에서 디자인 타임에 올바르게 표시되도록 구성 요소 및 컨트롤에 적용할 메타데이터 특성을 나열합니다.  
  
 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 디자인 타임 지원을 제공하는 편집기 및 디자이너와 같은 클래스를 구현하는 방법을 설명합니다.  
  
 [방법: 구성 요소 및 컨트롤 라이선스](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 컨트롤이나 구성 요소에서 라이선스를 구현하는 방법을 설명합니다.  
  
 또한 [디자인 타임에서 Windows Forms 컨트롤 개발](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\))을 참조하세요.
