---
title: "핵심 통신: HTTP-HTTPS 전송 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81eb778d70722cb44fa8dd4bc3f1152a12d87199
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-httphttps-transport-channels"></a>핵심 통신: HTTP/HTTPS 전송 채널
이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 전송 HTTP/HTTPS 채널에 의해 생성된 모든 예외를 보여 줍니다.  
  
## <a name="exception-list"></a>예외 목록  
  
|리소스 코드|리소스 문자열|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|지정된 가장 수준을 지정했습니다. HTTP Digest 인증은 명시적 자격 증명을 통해 사용되는 경우 '가장' 수준만 지원합니다.|  
|FramingContentTypeMismatch|지정된 콘텐츠 형식이 지정된 서비스에서 지원되지 않습니다. 클라이언트와 서비스 바인딩이 일치하지 않을 수 있습니다.|  
|Hosting_SslSettingsMisconfigured|지정된 서비스에 대한 Secure Sockets Layer 설정이 인터넷 정보 서비스의 설정과 일치하지 않습니다.|  
|HttpAuthSchemeAndClientCert|HTTPS 수신기 팩터리가 클라이언트 인증서 및 지정된 인증 스키마를 요구하도록 구성되었습니다. 그러나, 한 번에 한 가지 형태의 클라이언트 인증만 요구할 수 있습니다.|  
|HttpReceiveFailure|지정된 대상에 대한 HTTP 응답을 수신하는 동안 오류가 발생했습니다. 서비스 끝점 바인딩에서 HTTP 프로토콜을 사용하지 않고 있을 수 있습니다. 또한 서비스 종료로 인해 서버에서 HTTP 요청 컨텍스트가 종료되었을 수 있습니다. 자세한 내용은 서버 로그를 참조하세요.|  
|HttpRegistrationAccessDenied|HTTP가 지정된 URL을 등록할 수 없습니다. 프로세스에 이 네임스페이스에 대한 액세스 권한이 없습니다. 자세한 내용은 http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp를 참조하세요.|  
|HttpRegistrationAlreadyExists|HTTP가 지정된 URL을 등록할 수 없습니다. 다른 응용 프로그램에서 이미 HTTP.SYS를 통해 이 URL을 등록했습니다.|  
|HttpRegistrationPortInUse|지정된 TCP 포트를 다른 응용 프로그램에서 사용 중이므로 HTTP가 지정된 URL을 등록할 수 없습니다.|  
|HttpSendFailure|지정된 대상에 대한 HTTP 요청을 수행하는 동안 오류가 발생했습니다. 보안 바인딩 불일치가 원인이 아닌지 확인합니다. 또한 Secure Sockets Layer에 대해 서비스가 구성되어 있지 않은지 확인합니다.|  
|MessageXmlProtocolError|네트워크에서 수신한 XML에 문제가 있습니다. 자세한 내용은 내부 예외를 참조하세요.|  
|MissingContentType|지정된 대상에 대한 요청에 콘텐츠 형식이 없다는 것을 나타내는 오류를 수신자가 반환했습니다. 자세한 내용은 내부 예외를 참조하세요.|  
|ProxyAuthenticationLevelMismatch|HTTP 프록시 인증 자격 증명에서 대상 서버 인증 요구 사항보다 더 엄격한 상호 인증 요구 사항을 지정했습니다.|  
|ProxyImpersonationLevelMismatch|HTTP 프록시 인증 자격 증명에서 대상 서버 인증 제한보다 더 엄격한 가장 수준 제한을 지정했습니다.|  
|SecureChannelFailure|지정된 권한을 지닌 Secure Socket Layer/Transport Layer Security에 대해 보안 채널을 설정할 수 없습니다.|  
|TrustFailure|지정된 권한을 지닌 Secure Socket Layer/ Transport Layer Security 보안 채널에 대해 트러스트 관계를 설정할 수 없습니다.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|HttpTransportBinding 요소에서는 명시적 프록시 주소는 물론 UseDefaultWebProxy=true를 지정할 수 없습니다.|
