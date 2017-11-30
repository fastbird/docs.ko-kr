---
title: "산술 연산자(F#)"
description: "F # 프로그래밍 언어에서 사용할 수 있는 산술 연산자에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 75ddcfa3-564e-4382-80a3-f9da73d0f0ea
ms.openlocfilehash: 237b97c24f207b3a9b4661d66f029f1b18b8fec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="arithmetic-operators"></a><span data-ttu-id="c9ecf-104">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-104">Arithmetic Operators</span></span>

<span data-ttu-id="c9ecf-105">이 항목에서는 F # 언어에서 사용할 수 있는 산술 연산자를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-105">This topic describes arithmetic operators that are available in the F# language.</span></span>

## <a name="summary-of-binary-arithmetic-operators"></a><span data-ttu-id="c9ecf-106">이진 산술 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="c9ecf-106">Summary of Binary Arithmetic Operators</span></span>
<span data-ttu-id="c9ecf-107">다음 표에서 unboxed 정수 및 부동 소수점 형식에 사용할 수 있는 이진 산술 연산자를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-107">The following table summarizes the binary arithmetic operators that are available for unboxed integral and floating-point types.</span></span>

|<span data-ttu-id="c9ecf-108">이항 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-108">Binary operator</span></span>|<span data-ttu-id="c9ecf-109">노트</span><span class="sxs-lookup"><span data-stu-id="c9ecf-109">Notes</span></span>|
|---------------|-----|
|<span data-ttu-id="c9ecf-110">`+`(또한 플러스)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-110">`+` (addition, plus)</span></span>|<span data-ttu-id="c9ecf-111">선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-111">Unchecked.</span></span> <span data-ttu-id="c9ecf-112">합계와 함께 번호는 추가 하면 가능한 오버플로 조건을 형식에서 지 원하는 절대 최대값을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-112">Possible overflow condition when numbers are added together and the sum exceeds the maximum absolute value supported by the type.</span></span>|
|<span data-ttu-id="c9ecf-113">`-`(빼기, 빼기)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-113">`-` (subtraction, minus)</span></span>|<span data-ttu-id="c9ecf-114">선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-114">Unchecked.</span></span> <span data-ttu-id="c9ecf-115">언더플로 상태가 발생할 수 부호 없는 형식을 뺀 또는 부동 소수점 값이 너무 작아서 형식으로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-115">Possible underflow condition when unsigned types are subtracted, or when floating-point values are too small to be represented by the type.</span></span>|
|<span data-ttu-id="c9ecf-116">`*`(곱하기, 시간)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-116">`*` (multiplication, times)</span></span>|<span data-ttu-id="c9ecf-117">선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-117">Unchecked.</span></span> <span data-ttu-id="c9ecf-118">숫자를 곱해 하면 가능한 오버플로 조건 및 제품 형식에서 지 원하는 절대 최대값을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-118">Possible overflow condition when numbers are multiplied and the product exceeds the maximum absolute value supported by the type.</span></span>|
|<span data-ttu-id="c9ecf-119">`/`(나누기)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-119">`/` (division, divided by)</span></span>|<span data-ttu-id="c9ecf-120">0으로 나누기는 <xref:System.DivideByZeroException> 정수 계열 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-120">Division by zero causes a <xref:System.DivideByZeroException> for integral types.</span></span> <span data-ttu-id="c9ecf-121">부동 소수점 형식에 대 한 0으로 나누기 하면 특수 한 부동 소수점 값 `+Infinity` 또는 `-Infinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-121">For floating-point types, division by zero gives you the special floating-point values `+Infinity` or `-Infinity`.</span></span> <span data-ttu-id="c9ecf-122">이기도 가능한 언더플로 조건을 부동 소수점 숫자는 너무 작아서 형식으로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-122">There is also a possible underflow condition when a floating-point number is too small to be represented by the type.</span></span>|
|<span data-ttu-id="c9ecf-123">`%`(계수, mod)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-123">`%` (modulus, mod)</span></span>|<span data-ttu-id="c9ecf-124">나누기 연산의 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-124">Returns the remainder of a division operation.</span></span> <span data-ttu-id="c9ecf-125">결과의 부호가 첫 번째 피연산자의 부호와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-125">The sign of the result is the same as the sign of the first operand.</span></span>|
|<span data-ttu-id="c9ecf-126">`**`(의 지 수)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-126">`**` (exponentiation, to the power of)</span></span>|<span data-ttu-id="c9ecf-127">결과 형식에 대 한 절대 최대값을 초과 하는 경우 가능한 오버플로 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-127">Possible overflow condition when the result exceeds the maximum absolute value for the type.</span></span><br /><br /><span data-ttu-id="c9ecf-128">지 수 연산자 부동 소수점 형식 에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-128">The exponentiation operator works only with floating-point types.</span></span>|

## <a name="summary-of-unary-arithmetic-operators"></a><span data-ttu-id="c9ecf-129">단항 산술 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="c9ecf-129">Summary of Unary Arithmetic Operators</span></span>
<span data-ttu-id="c9ecf-130">다음 표에서 정수 및 부동 소수점 형식에 사용할 수 있는 단항 산술 연산자를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-130">The following table summarizes the unary arithmetic operators that are available for integral and floating-point types.</span></span>


|<span data-ttu-id="c9ecf-131">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-131">Unary operator</span></span>|<span data-ttu-id="c9ecf-132">노트</span><span class="sxs-lookup"><span data-stu-id="c9ecf-132">Notes</span></span>|
|--------------|-----|
|<span data-ttu-id="c9ecf-133">`+`(양수)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-133">`+` (positive)</span></span>|<span data-ttu-id="c9ecf-134">모든 산술 식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-134">Can be applied to any arithmetic expression.</span></span> <span data-ttu-id="c9ecf-135">값의 부호는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-135">Does not change the sign of the value.</span></span>|
|<span data-ttu-id="c9ecf-136">`-`(부정, 음수)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-136">`-` (negation, negative)</span></span>|<span data-ttu-id="c9ecf-137">모든 산술 식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-137">Can be applied to any arithmetic expression.</span></span> <span data-ttu-id="c9ecf-138">값의 부호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-138">Changes the sign of the value.</span></span>|
<span data-ttu-id="c9ecf-139">주위에 배치 하에서 오버플로 또는 언더플로 정수 계열 형식에 대 한 동작이입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-139">The behavior at overflow or underflow for integral types is to wrap around.</span></span> <span data-ttu-id="c9ecf-140">이렇게 하면 잘못 된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-140">This causes an incorrect result.</span></span> <span data-ttu-id="c9ecf-141">정수 오버플로 소프트웨어에 대 한 계정에 기록 되지 않습니다 때 보안 문제를 일으킬 수 있는 잠재적으로 심각한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-141">Integer overflow is a potentially serious problem that can contribute to security issues when software is not written to account for it.</span></span> <span data-ttu-id="c9ecf-142">응용 프로그램에 대 한 우려 경우 하에서 확인 된 연산자를 사용 하 여 `Microsoft.FSharp.Core.Operators.Checked`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-142">If this is a concern for your application, consider using the checked operators in `Microsoft.FSharp.Core.Operators.Checked`.</span></span>


## <a name="summary-of-binary-comparison-operators"></a><span data-ttu-id="c9ecf-143">이진 비교 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="c9ecf-143">Summary of Binary Comparison Operators</span></span>
<span data-ttu-id="c9ecf-144">다음 표에서 정수 및 부동 소수점 형식에 사용할 수 있는 이진 비교 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-144">The following table shows the binary comparison operators that are available for integral and floating-point types.</span></span> <span data-ttu-id="c9ecf-145">이러한 연산자의 반환 값 형식 `bool`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-145">These operators return values of type `bool`.</span></span>

<span data-ttu-id="c9ecf-146">부동 소수점 숫자를 직접 비교할 수 없습니다, 동등 여부에 대 한 IEEE 부동 소수점 표시 된 값이 같은지를 지원 하지 않으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-146">Floating-point numbers should never be directly compared for equality, because the IEEE floating-point representation does not support an exact equality operation.</span></span> <span data-ttu-id="c9ecf-147">두 숫자 코드를 검사 하 여 동일한 것으로 쉽게 확인할 수 있는 서로 다른 비트 표현의 있을 실제로 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-147">Two numbers that you can easily verify to be equal by inspecting the code might actually have different bit representations.</span></span>



|<span data-ttu-id="c9ecf-148">연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-148">Operator</span></span>|<span data-ttu-id="c9ecf-149">노트</span><span class="sxs-lookup"><span data-stu-id="c9ecf-149">Notes</span></span>|
|--------|-----|
|<span data-ttu-id="c9ecf-150">`=`(같음)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-150">`=` (equality, equals)</span></span>|<span data-ttu-id="c9ecf-151">할당 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-151">This is not an assignment operator.</span></span> <span data-ttu-id="c9ecf-152">비교에 대해서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-152">It is used only for comparison.</span></span> <span data-ttu-id="c9ecf-153">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-153">This is a generic operator.</span></span>|
|<span data-ttu-id="c9ecf-154">`>`(보다 큼)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-154">`>` (greater than)</span></span>|<span data-ttu-id="c9ecf-155">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-155">This is a generic operator.</span></span>|
|<span data-ttu-id="c9ecf-156">`<`(보다 작음)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-156">`<` (less than)</span></span>|<span data-ttu-id="c9ecf-157">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-157">This is a generic operator.</span></span>|
|<span data-ttu-id="c9ecf-158">`>=`(크거나 같음)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-158">`>=` (greater than or equals)</span></span>|<span data-ttu-id="c9ecf-159">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-159">This is a generic operator.</span></span>|
|<span data-ttu-id="c9ecf-160">`<=`(보다 작거나 같음)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-160">`<=` (less than or equals)</span></span>|<span data-ttu-id="c9ecf-161">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-161">This is a generic operator.</span></span>|
|<span data-ttu-id="c9ecf-162">`<>`(같지 않음)</span><span class="sxs-lookup"><span data-stu-id="c9ecf-162">`<>` (not equal)</span></span>|<span data-ttu-id="c9ecf-163">일반 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-163">This is a generic operator.</span></span>|

## <a name="overloaded-and-generic-operators"></a><span data-ttu-id="c9ecf-164">제네릭 및 오버 로드 된 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-164">Overloaded and Generic Operators</span></span>
<span data-ttu-id="c9ecf-165">에 정의 된 모든이 여기에 나온 연산자는 **Microsoft.FSharp.Core.Operators** 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-165">All of the operators discussed in this topic are defined in the **Microsoft.FSharp.Core.Operators** namespace.</span></span> <span data-ttu-id="c9ecf-166">일부 연산자는 정적으로 확인 된 형식 매개 변수를 사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-166">Some of the operators are defined by using statically resolved type parameters.</span></span> <span data-ttu-id="c9ecf-167">해당 연산자를 사용 하는 각 특정 형식에 대 한 개별 정의 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-167">This means that there are individual definitions for each specific type that works with that operator.</span></span> <span data-ttu-id="c9ecf-168">단항 및 이항 산술 및 비트 연산자의 모든이 범주에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-168">All of the unary and binary arithmetic and bitwise operators are in this category.</span></span> <span data-ttu-id="c9ecf-169">비교 연산자는 제네릭 및 따라서 하지 기본 산술 형식 뿐, 모든 유형과 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-169">The comparison operators are generic and therefore work with any type, not just primitive arithmetic types.</span></span> <span data-ttu-id="c9ecf-170">구별 된 공용 구조체 및 레코드 형식을 F # 컴파일러에 의해 생성 되는 고유한 사용자 지정 구현이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-170">Discriminated union and record types have their own custom implementations that are generated by the F# compiler.</span></span> <span data-ttu-id="c9ecf-171">메서드를 사용 하는 클래스 형식 <xref:System.Object.Equals%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-171">Class types use the method <xref:System.Object.Equals%2A>.</span></span>

<span data-ttu-id="c9ecf-172">일반 연산자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-172">The generic operators are customizable.</span></span> <span data-ttu-id="c9ecf-173">비교 함수를 사용자 지정 하려면 재정의 <xref:System.Object.Equals%2A> 사용자 고유의 사용자 지정 같음 비교를 제공 하 고 다음 구현에 <xref:System.IComparable>합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-173">To customize the comparison functions, override <xref:System.Object.Equals%2A> to provide your own custom equality comparison, and then implement <xref:System.IComparable>.</span></span> <span data-ttu-id="c9ecf-174"><xref:System.IComparable?displayProperty=nameWithType> 인터페이스에는 단일 메서드는 <xref:System.IComparable.CompareTo%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-174">The <xref:System.IComparable?displayProperty=nameWithType> interface has a single method, the <xref:System.IComparable.CompareTo%2A> method.</span></span>


## <a name="operators-and-type-inference"></a><span data-ttu-id="c9ecf-175">연산자 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="c9ecf-175">Operators and Type Inference</span></span>
<span data-ttu-id="c9ecf-176">식에서 연산자를 사용 하는 연산자에는 형식 유추를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-176">The use of an operator in an expression constrains type inference on that operator.</span></span> <span data-ttu-id="c9ecf-177">또한 연산자의 사용 방지 연산자는 산술 형식 의미 하기 때문에 자동 일반화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-177">Also, the use of operators prevents automatic generalization, because the use of operators implies an arithmetic type.</span></span> <span data-ttu-id="c9ecf-178">다른 정보가 없는 경우, F # 컴파일러에서 유추 `int` 산술 식의 형식으로.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-178">In the absence of any other information, the F# compiler infers `int` as the type of arithmetic expressions.</span></span> <span data-ttu-id="c9ecf-179">다른 형식을 지정 하 여이 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-179">You can override this behavior by specifying another type.</span></span> <span data-ttu-id="c9ecf-180">인수 형식 및 반환 형식은 따라서 `function1` 다음 코드에서는 것으로 유추 됩니다 `int`에 대 한 형식 `function2` 것으로 유추 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9ecf-180">Thus the argument types and return type of `function1` in the following code are inferred to be `int`, but the types for `function2` are inferred to be `float`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]
    
## <a name="see-also"></a><span data-ttu-id="c9ecf-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9ecf-181">See Also</span></span>
[<span data-ttu-id="c9ecf-182">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="c9ecf-182">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="c9ecf-183">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="c9ecf-183">Operator Overloading</span></span>](../operator-overloading.md)

[<span data-ttu-id="c9ecf-184">비트 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-184">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="c9ecf-185">부울 연산자</span><span class="sxs-lookup"><span data-stu-id="c9ecf-185">Boolean Operators</span></span>](boolean-operators.md)