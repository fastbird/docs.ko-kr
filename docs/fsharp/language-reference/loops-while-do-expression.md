---
title: "루프: while...do 식(F#)"
description: "참조 방식을 while... 않습니다 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (루프)을 수행 하는데 사용 됩니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 6a186d75dcda383764949c2cd3b09bc9e3d1080a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="loops-whiledo-expression"></a>루프: while...do 식

`while...do` 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (루프)을 수행 하는데 사용 됩니다.


## <a name="syntax"></a>구문

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>설명
*테스트 식* 를 평가 합니다;이 경우 `true`, *본문 식* 실행 될 테스트 식이 다시 계산 됩니다. *본문 식* 형식이 있어야 `unit`합니다. 테스트 식이 `false`, 반복이 끝납니다.

다음 예제에서는 `while...do` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

이전 코드의 출력은 1에서 20 사이의 난수 이루어진은 10 스트림입니다.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
사용할 수 있습니다 `while...do` 시퀀스 식 및 다른 계산 식, 사용자 지정된 된 버전의 경우는 `while...do` 식이 사용 됩니다. 자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[루프: `for...in` 식](loops-for-in-expression.md)

[루프: `for...to` 식](loops-for-to-expression.md)