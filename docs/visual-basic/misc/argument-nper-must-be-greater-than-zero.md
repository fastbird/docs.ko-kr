---
title: "인수 &#39; NPer &#39; 0 보다 커야 합니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa19f1842bcfa82908fe79f6fda69bbc5dd9499c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="argument-39nper39-must-be-greater-than-zero"></a>인수 &#39; NPer &#39; 0 보다 커야 합니다.
일정 기간의 고정 지불액과 고정 이자율을 기준으로 연금의 기간 수를 지정하는 `NPer` 을 반환하는 `Double` 함수에는 0보다 큰 인수가 필요합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   식에서 인수의 철자를 검사합니다. 철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.  
  
-   이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빌드에 없음: NPer 함수](http://msdn.microsoft.com/en-us/56567d16-29f7-4928-b05f-b4cd56d4fd42)  
 [값 또는 참조로 인수 전달](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
