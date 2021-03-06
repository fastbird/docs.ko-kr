---
title: "XML 스키마 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a>XML 스키마 사용
XML 문서 구조, 요소 관계, 데이터 형식, 내용 제약 조건 등을 정의하려면 DTD(문서 종류 정의) 또는 XSD(XML 스키마 정의 언어) 스키마를 사용합니다. XML 문서가 제대로 구성된 것으로 간주되더라도 W3C(World Wide Web 컨소시엄) XML(Extensible Markup Language) 1.0 권장 사항에 정의된 구문 요구 사항을 모두 만족할 경우 제대로 구성되고 DTD나 스키마에 정의된 제약 조건을 준수해야만 유효한 것으로 간주됩니다. 그러므로 유효한 모든 XML 문서가 제대로 구성되었더라도 제대로 구성된 XML 문서가 모두 유효한 것은 아닙니다.  
  
 XML에 대 한 자세한 내용은 참조는 [W3C XML 1.0 권장 사항](http://go.microsoft.com/fwlink/?linkid=7269)합니다. XML 스키마에 대 한 자세한 내용은 참조는 [W3C XML 스키마 1 부: 구조 권장 사항](http://go.microsoft.com/fwlink/?linkid=48881) 및 [W3C XML Schema Part 2: Datatypes 권장 사항을](http://go.microsoft.com/fwlink/?linkid=17392) 권장 사항입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [XML SOM(스키마 개체 모델)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 파일에서 XSD(XML 스키마 정의 언어) 스키마를 읽거나 프로그래밍 방식으로 메모리 내 스키마를 만들 수 있는 클래스 집합을 제공하는 <xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스의 SOM(스키마 개체 모델)에 대해 설명합니다.  
  
 [스키마 컴파일 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 XSD 스키마를 저장하고 유효성을 검사할 수 있는 캐시인 <xref:System.Xml.Schema.XmlSchemaSet> 클래스에 대해 설명합니다.  
  
 [XmlSchemaValidator 밀어넣기 기반 유효성 검사](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 밀어넣기 기반 방식으로 XSD 스키마에 대해 XML 데이터의 유효성을 검사할 수 있는 효과적인 고성능 메커니즘을 제공하는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스에 대해 설명합니다.  
  
 [XML 스키마 유추](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 <xref:System.Xml.Schema.XmlSchemaInference> 클래스를 사용하여 XML 문서 구조에서 XSD 스키마를 유추하는 방법을 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>관련 단원  
 [DOM에서 XML 문서 유효성 검사](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 DOM(문서 개체 모델)에서 XML의 유효성을 검사하는 방법을 설명합니다. XML을 DOM에 로드할 때 유효성을 검사하거나 DOM에서 이전에 무효화한 XML 문서의 유효성을 검사할 수 있습니다.  
  
 [XPathNavigator를 사용 하 여 스키마 유효성 검사](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <xref:System.Xml.XPath.XPathNavigator> 클래스를 사용하여 탐색 및 편집하는 XML의 유효성 검사 방법을 설명합니다.
