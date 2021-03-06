---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71ed2fc6e4e5407cdf8c3e2334dcc0c16a00cf83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.  
  
\<시스템입니다. ServiceModel >  
\<바인딩 >  
\<netHttpBinding >  
  
## <a name="syntax"></a>구문  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|createNotificationOnConnection|연결 시 알림이 보내지는지 여부를 지정합니다.|  
|disablePayloadMasking|WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.|  
|keepAliveInterval|상태 유지 간격을 지정합니다.|  
|maxPendingConnections|서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.|  
|receiveBufferSize|수신 버퍼의 크기를 지정합니다.|  
|sendBufferSize|전송 버퍼의 크기를 지정합니다.|  
|subProtocol|WebSocket 하위 프로토콜을 지정합니다.|  
|transportUsage|WebSocket을 사용할 시기를 지정합니다.|  
  
## <a name="transportusage-attribute"></a>transportUsage 특성  
  
|값|설명|  
|-----------|-----------------|  
|WhenDuplex|이중 계약인 경우 WebSocket 프로토콜을 사용합니다.|  
|Always|계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.|  
|Never|WebSocket 프로토콜을 사용하지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|\<netHttpBinding >|NetHttpBinding을 지정합니다.|  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 \<webSocketSettings > 요소입니다.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)
