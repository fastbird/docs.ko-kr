---
title: "방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbac99770b5cbb7dacb0468e1a892956fda6b79c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예에서 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 의 위치에 애니메이션을 적용 하는 데 사용 되는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 3D 장면에 있습니다. 또한 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 3D 장면에 카메라가 가리키는 방향에 애니메이션을 적용 하는 데 사용 됩니다. 모두 이러한 애니메이션 일련의 애니메이션 효과 생성 하는 여러 키 프레임을 사용 합니다.  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 부드러운 값 사이의 선형 보간을 만드는 데 사용 됩니다.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 값 (보간 없음) 사이의 급격 한 "이동"을 만드는 데 사용 됩니다.  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> 변수 전환에 따라 값을 만드는 데 사용 되는 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 속성입니다. 아래 예제에서 애니메이션 서서히 시작 되 다가 시간 세그먼트의 끝으로, 갈수록 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
