---
title: "방법: 페이지로 이동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa4d0881d7dcdb2c56c66c5617652ec1a2cbc374
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-to-a-page"></a>방법: 페이지로 이동
이 예제는 페이지를 탐색할 수 있습니다에서 여러 가지 방법으로 <xref:System.Windows.Navigation.NavigationWindow>합니다.  
  
## <a name="example"></a>예제  
 수는 <xref:System.Windows.Navigation.NavigationWindow> 다음 중 하나를 사용 하 여 페이지를 탐색할 수 있습니다.  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 메서드  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]상대 또는 절대 수 있습니다. 자세한 내용은 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>
