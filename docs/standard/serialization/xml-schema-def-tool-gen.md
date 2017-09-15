---
title: 'How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 3d0d7a6fa5f8b6108567de02cfaec6f1fea71796
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents
XML 스키마 정의 도구(Xsd.exe)를 사용하면 클래스를 설명하는 XML 스키마를 생성하거나 XML 스키마로 정의된 클래스를 생성할 수 있습니다. 다음 절차에서는 이러한 작업을 수행하는 방법을 보여 줍니다.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>특정 스키마를 따르는 클래스를 생성하려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  XML 스키마를 XML 스키마 정의 도구에 인수로 전달합니다. 그러면 예를 들어 XML 스키마에 정확하게 일치하는 클래스 집합이 만들어 집니다.  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     도구는 2001년 3월 16일자 World Wide Web 컨소시엄 XML 사양을 참조하는 스키마만 처리할 수 있습니다. 즉, XML 스키마 네임스페이스는 다음 예제와 같이 "http://www.w3.org/2001/XMLSchema"여야 합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  필요에 따라 메서드, 속성 또는 필드로 클래스를 수정합니다. 특성을 사용하여 클래스를 수정하는 방법에 대한 자세한 내용은 [특성을 사용하여 XML Serialization 제어](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) 및 [인코딩된 SOAP Serialization을 제어하는 특성](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)을 참조하세요.  
  
 클래스의 인스턴스가 serialize될 때 생성되는 XML 스트림의 스키마를 검사하는 것이 유용할 때가 있습니다. 예를 들어 스키마를 다른 사람이 사용할 수 있도록 게시하거나 준수를 위해 다른 스키마와 비교할 수 있습니다.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>클래스 집합에서 XML 스키마 문서를 생성하려면  
  
1.  클래스를 DLL로 컴파일합니다.  
  
2.  명령 프롬프트를 엽니다.  
  
3.  DLL을 Xsd.exe에 인수로 전달합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     스키마가 이름 "schema0.xsd"로 시작하여 기록됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataSet>   
 [XML 스키마 정의 도구 및 XML serialization](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [XML serialization 소개](../../../docs/standard/serialization/introducing-xml-serialization.md)   
 [XML 스키마 정의 도구(Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)   
 <xref:System.Xml.Serialization.XmlSerializer>   
 [방법: 개체 직렬화](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [방법: 개체 deserialize](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
