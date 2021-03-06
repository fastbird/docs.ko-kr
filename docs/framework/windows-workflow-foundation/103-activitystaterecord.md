---
title: 103 - ActivityStateRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41621ccc634fec9212b84e88c089527b9e502648
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="103---activitystaterecord"></a>103 - ActivityStateRecord
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|Id|103|  
|키워드|EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 워크플로 인스턴스 내의 활동에서 ActivityStateRecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## <a name="message"></a>메시지  
 TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간(UTC)|  
|상태|xs:string|활동의 상태|  
|이름|xs:string|이벤트를 내보낸 활동의 표시 이름|  
|ActivityId|xs:string|내보내는 활동의 활동 ID|  
|ActivityInstanceId|xs:string|내보내는 활동의 활동 인스턴스 ID|  
|ActivityTypeName|xs:string|내보내는 활동의 형식 이름|  
|인수|xs:string|이 이벤트와 함께 추적된 인수입니다.  값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "argumentName" type = "> a r g\<항목/>\<항목/>입니다.  추적 된 인수가 경우 문자열에 포함 되어 \<항목 / >입니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.  ToString()에 의해 반환되는 값으로 string, char, bool, int, short, long, uint, ushort, ulong, System.Single, float, double, System.Guid, System.DateTimeOffset, System.DateTime 형식이 저장됩니다.  모든 다른 형식은 System.Runtime.Serialization.NetDataContractSerializer를 사용하여 serialize됩니다.|  
|변수|xs:string|이 이벤트와 함께 추적된 변수입니다.  값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "variableName" type = "> variableValue\<항목/>\<항목/>입니다.  추적 된 변수가 경우 문자열에 포함 되어 \<항목 / >입니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 사용 하 여 변수 값을 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.  ToString()에 의해 반환되는 값으로 string, char, bool, int, short, long, uint, ushort, ulong, System.Single, float, double, System.Guid, System.DateTimeOffset, System.DateTime 형식이 저장됩니다.  모든 다른 형식은 System.Runtime.Serialization.NetDataContractSerializer를 사용하여 serialize됩니다.|  
|주석|xs:string|이 이벤트에 추가된 주석입니다.  값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "annotationName" type = "> annotationValue\<항목/>\<항목/>입니다.  주석을 지정 하지 않으면 문자열을 포함 하는 경우 \<항목 / >입니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|HostReference|xs:string|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.  해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName' 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
