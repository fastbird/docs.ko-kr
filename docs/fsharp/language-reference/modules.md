---
title: "모듈(F#)"
description: "F # 모듈은 F # 코드 값, 형식, F # 프로그램에서 함수 값 등의 그룹화 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 46de2d18-da51-40fa-a262-92edecada79d
ms.openlocfilehash: 89401c1f889be6c5585a302e3a7ac62478573b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="modules"></a><span data-ttu-id="b3f64-104">모듈</span><span class="sxs-lookup"><span data-stu-id="b3f64-104">Modules</span></span>

<span data-ttu-id="b3f64-105">F # 언어의 컨텍스트에서 *모듈* 그룹 값, 형식 및 F # 프로그램에서 함수 값을 같은 F # 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-105">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="b3f64-106">모듈로 코드를 그룹화하면 관련 코드를 함께 유지하고, 프로그램의 이름 충돌을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-106">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3f64-107">구문</span><span class="sxs-lookup"><span data-stu-id="b3f64-107">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="b3f64-108">설명</span><span class="sxs-lookup"><span data-stu-id="b3f64-108">Remarks</span></span>
<span data-ttu-id="b3f64-109">F # 모듈은 F # 코드 구문 형식, 값, 함수 값의 코드 등의 그룹 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="b3f64-109">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="b3f64-110">정적 멤버만 있는 공용 언어 런타임 (CLR) 클래스 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-110">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="b3f64-111">두 가지 방법으로 전체 파일 모듈에 포함 되는지 여부에 따라 모듈 선언의: 최상위 모듈 선언 및 로컬 모듈 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-111">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="b3f64-112">최상위 모듈 선언 모듈에 전체 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-112">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="b3f64-113">최상위 모듈 선언은 파일의 첫 번째 선언 에서만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-113">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="b3f64-114">선택적 최상위 모듈 선언에 대 한 구문에서 *정규화 된 네임 스페이스* 모듈을 포함 하는 중첩 된 네임 스페이스 이름의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-114">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="b3f64-115">정규화 된 네임 스페이스는 이전에 선언 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-115">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="b3f64-116">최상위 모듈의 선언 들여쓰기 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-116">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="b3f64-117">들여쓰기 로컬 모듈의 모든 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-117">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="b3f64-118">로컬 모듈 선언에 해당 모듈 선언 아래 들여쓴 선언에만 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-118">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="b3f64-119">모든 로컬 모듈을 포함 하는 파일의 전체 내용을 확장명 없이 파일 이름이 동일한 암시적으로 만든된 최상위 모듈의 일부가 코드 파일 최상위 모듈 선언 또는 네임 스페이스 선언으로 시작 되지 않을 경우 첫 번째 글자를 대문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-119">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="b3f64-120">다음 파일을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-120">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="b3f64-121">이런이 방식으로 작성 된 경우에 따라이 파일에 컴파일되는:</span><span class="sxs-lookup"><span data-stu-id="b3f64-121">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="b3f64-122">여러 모듈 파일에 있는 경우에 각 모듈에 대 한 로컬 모듈 선언을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-122">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="b3f64-123">바깥쪽 네임 스페이스 선언 된 경우 이러한 모듈은 바깥쪽 네임 스페이스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-123">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="b3f64-124">바깥쪽 네임 스페이스 선언 되지 않은 경우의 모듈은 암시적으로 만든된 최상위 모듈의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-124">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="b3f64-125">다음 코드 예제에서는 여러 모듈을 포함 하는 코드 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-125">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="b3f64-126">컴파일러는 암시적으로 라는 최상위 모듈을 만듭니다 `Multiplemodules`, 및 `MyModule1` 및 `MyModule2` 최상위 해당 모듈에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-126">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="b3f64-127">단일 컴파일 또는 프로젝트에서 여러 파일 또는 라이브러리를 빌드하는 경우 파일의 맨 위에 선언은 모듈 또는 네임 스페이스 선언을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-127">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="b3f64-128">F # 컴파일러만 모듈 이름을 암시적으로 때 결정 프로젝트 또는 컴파일 명령줄에 파일이 하나만 있으며 응용 프로그램을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-128">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="b3f64-129">*접근성 한정자* 다음 중 하나일 수 있습니다: `public`, `private`, `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-129">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="b3f64-130">자세한 내용은 [액세스 제어](access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3f64-130">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="b3f64-131">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-131">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="b3f64-132">모듈에서 참조 하는 코드</span><span class="sxs-lookup"><span data-stu-id="b3f64-132">Referencing Code in Modules</span></span>
<span data-ttu-id="b3f64-133">다른 모듈에서 함수, 유형 및 값을 참조할 때는 정규화 된 이름을 사용 하거나 모듈을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-133">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="b3f64-134">정규화 된 이름을 사용 하는 경우 네임 스페이스, 모듈 및 필요한 프로그램 요소에 대 한 식별자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-134">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="b3f64-135">구분 해야 정규화 된 경로 각 부분의 점 (.), 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-135">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="b3f64-136">모듈 또는 하나 이상의 코드를 간소화 하기 위해 네임 스페이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-136">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="b3f64-137">여는 네임 스페이스 및 모듈에 대 한 자세한 내용은 참조 [가져오기 선언:는 `open` 키워드](import-declarations-the-open-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-137">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="b3f64-138">다음 코드 예제에서는 파일의 끝까지 모든 코드를 포함 하는 최상위 모듈을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-138">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="b3f64-139">동일한 프로젝트에 다른 파일에서이 코드를 사용 하려면 정규화 된 이름을 사용 하거나 또는 열면 모듈의 함수를 사용 하기 전에 다음 예에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-139">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="b3f64-140">중첩된 모듈</span><span class="sxs-lookup"><span data-stu-id="b3f64-140">Nested Modules</span></span>
<span data-ttu-id="b3f64-141">모듈은 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-141">Modules can be nested.</span></span> <span data-ttu-id="b3f64-142">외부 모듈 선언 내부 모듈을 새 모듈이 아니라 된다는를 만큼 내부 모듈을 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-142">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="b3f64-143">예를 들어 다음 두 가지 예제를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-143">For example, compare the following two examples.</span></span> <span data-ttu-id="b3f64-144">모듈 `Z` 는 다음 코드의 내부 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-144">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="b3f64-145">하지만 모듈 `Z` 모듈에는 형제인 `Y` 다음 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-145">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="b3f64-146">모듈 `Z` 모듈의 다른 선언 뿌리 들여쓰지 않습니다 때문에 다음 코드에서는 형제 모듈 이기도 `Y`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-146">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="b3f64-147">마지막으로, 외부 모듈에 선언이 없고 하 고 다른 모듈 선언 바로 뒤, 새 모듈 선언 내부 모듈을 것으로 간주 됩니다는 컴파일러에서 경고 메시지가 두 번째 모듈 정의 하는 경우 보다 더 멀게 들여쓰지 않습니다는 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-147">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="b3f64-148">이 경고를 제거 하려면 내부 모듈을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-148">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="b3f64-149">단일 외부 모듈에 포함 되도록 파일의 모든 코드를 원하는 경우 내부 모듈 외부 모듈 등호 필요 하지 않으며 외부 모듈에는 모든 내부 모듈 선언을 포함 하 여 선언 들 여 쓰도록 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-149">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="b3f64-150">내부 모듈 선언 안에 선언을 들 여 쓸 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-150">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="b3f64-151">다음 코드에서는이 사례를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-151">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="module-rec-allowing-mutual-recursive-code-at-the-module-level"></a><span data-ttu-id="b3f64-152">모듈 `rec`: 모듈 수준에서 상호 재귀 코드</span><span class="sxs-lookup"><span data-stu-id="b3f64-152">Module `rec`: allowing mutual recursive code at the module level</span></span>

<span data-ttu-id="b3f64-153">F # 4.1 상호는 재귀적일 수에 포함 된 모든 코드를 허용 하는 모듈의 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-153">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="b3f64-154">통해 이렇게 `module rec`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-154">This is done via `module rec`.</span></span>  <span data-ttu-id="b3f64-155">사용 하 여 `module rec` 의 형식 및 모듈 간에 상호 참조 코드를 작성할 수 없는 일부 그리고를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-155">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="b3f64-156">다음은 이러한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-156">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

    type BananaPeel() = class end

    type Banana(orientation : Orientation) =
        member val IsPeeled = false with get, set
        member val Orientation = orientation with get, set
        member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set
        
        member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
        member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

    module private BananaHelpers =
        let peel (b : Banana) =
            let flip banana =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides banana =
                for side in banana.Sides do
                    if side = Unpeeled then
                        side <- Peeled

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

<span data-ttu-id="b3f64-157">예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-157">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="b3f64-158">또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-158">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="b3f64-159">F #에서 express를 제거한 경우 가능 하지 않습니다이 `rec` 에서 키워드는 `RecursiveModule` 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-159">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="b3f64-160">이 기능을 확장할 수 또한 [네임 스페이스](namespaces.md) F # 4.1을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-160">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3f64-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3f64-161">See Also</span></span>

<span data-ttu-id="b3f64-162">[F # 언어 참조](index.md)
[네임 스페이스](namespaces.md)
[F # RFC FS-1009-파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span><span class="sxs-lookup"><span data-stu-id="b3f64-162">[F# Language Reference](index.md)
[Namespaces](namespaces.md)
[F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span></span>