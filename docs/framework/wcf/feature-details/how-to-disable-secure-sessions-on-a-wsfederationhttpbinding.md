---
title: "방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
caps.latest.revision: "16"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: bb2970209814fbbee9f71f0263a4d3d4f02f3e20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정
일부 서비스에서 페더레이션 자격 증명을 필요로 하지만 보안 세션을 지원하지 않을 수도 있습니다. 이 경우 보안 세션 기능을 사용하지 않도록 설정해야 합니다. 와 달리는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, <xref:System.ServiceModel.WSFederationHttpBinding> 클래스 보안 세션을 사용 하지 않도록 설정 하는 방법을 제공 하지 않습니다는 서비스와 통신할 때. 대신 보안 세션 설정을 부트스트랩으로 대체하는 사용자 지정 바인딩을 만들어야 합니다.  
  
 이 항목에서는 <xref:System.ServiceModel.WSFederationHttpBinding>에 포함된 바인딩 요소를 수정하여 사용자 지정 바인딩을 만드는 방법을 보여 줍니다. 보안 세션을 사용하지 않는 점만 제외하고 결과는 <xref:System.ServiceModel.WSFederationHttpBinding>과 동일합니다.  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a>보안 세션을 사용하지 않고 사용자 지정 페더레이션 바인딩을 만들려면  
  
1.  구성 파일에서 로드하거나 코드에서 명령적으로 <xref:System.ServiceModel.WSFederationHttpBinding> 클래스 인스턴스를 만듭니다.  
  
2.  <xref:System.ServiceModel.WSFederationHttpBinding>을 <xref:System.ServiceModel.Channels.CustomBinding>으로 복제합니다.  
  
3.  <xref:System.ServiceModel.Channels.SecurityBindingElement>에서 <xref:System.ServiceModel.Channels.CustomBinding>를 찾습니다.  
  
4.  <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>에서 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 찾습니다.  
  
5.  원래 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>의 부트스트랩 보안 바인딩 요소로 바꿉니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 보안 세션을 사용하지 않고 사용자 지정 페더레이션 바인딩을 만듭니다.  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   코드 예제를 컴파일하려면 System.ServiceModel.dll 어셈블리를 참조하는 프로젝트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩 및 보안](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
