---
title: ファイル構造 |Microsoft Docs
description: 'Q # ファイル構造'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185190"
---
# <a name="file-structure"></a><span data-ttu-id="f5dfd-103">ファイル構造</span><span class="sxs-lookup"><span data-stu-id="f5dfd-103">File Structure</span></span>

<span data-ttu-id="f5dfd-104">Q # ファイルは、一連の名前空間宣言で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="f5dfd-105">各名前空間の宣言には、ユーザー定義型、操作、および関数の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="f5dfd-106">名前空間宣言には、任意の数の宣言を任意の順序で含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="f5dfd-107">名前空間の宣言の外側に表示されるテキストは、コメントだけです。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="f5dfd-108">特に、名前空間のドキュメントコメントは、宣言の前に記述します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="f5dfd-109">名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="f5dfd-109">Namespace Declarations</span></span>

<span data-ttu-id="f5dfd-110">Q # ファイルには、通常、名前空間宣言が1つだけ含まれますが、(空またはコメントを含む) は使用できません。また、複数の名前空間を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="f5dfd-111">名前空間宣言を入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="f5dfd-112">同じ名前の型、操作、または関数の宣言がない限り、同じ名前空間を複数の Q # ファイルで宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="f5dfd-113">特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="f5dfd-114">名前空間宣言は、キーワード `namespace`、名前空間の名前、始めかっこ `{`、名前空間に含まれる宣言、および終わりかっこ `}`で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="f5dfd-115">名前空間名は、`.`ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="f5dfd-116">たとえば、`MyQuantumStuff` と `Microsoft.Quantum.Canon` は有効な名前空間名です。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="f5dfd-117">慣例により、名前空間名に含まれる記号は大文字になりますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="f5dfd-118">宣言は、名前空間の宣言内で任意の順序で記述できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="f5dfd-119">ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="f5dfd-120">オープンディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f5dfd-120">Open Directives</span></span>

<span data-ttu-id="f5dfd-121">名前空間ブロック内では、`open` ディレクティブを使用して、特定の名前空間で定義されているすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="f5dfd-122">このような `open` ディレクティブは、`open` キーワードで構成され、その後に、名前空間が開かれ、セミコロンが終了します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="f5dfd-123">たとえば、</span><span class="sxs-lookup"><span data-stu-id="f5dfd-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="f5dfd-124">必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="f5dfd-125">この短い名前は、キーワード `as` の後に、必要な短い名前をセミコロンの前に `open` ディレクティブで追加することによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="f5dfd-126">すべての `open` ディレクティブは、namespace ブロック内の `function`、`operation`、または `newtype` 宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="f5dfd-127">`open` ディレクティブは、ファイル内の名前空間ブロック全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="f5dfd-128">ユーザー定義型の宣言</span><span class="sxs-lookup"><span data-stu-id="f5dfd-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="f5dfd-129">Q # は、ユーザーが新しいユーザー定義型を宣言する方法を提供します。詳細については、「 [q # type model](xref:microsoft.quantum.language.type-model) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="f5dfd-130">基本型が同一の場合でも、ユーザー定義型は区別されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="f5dfd-131">特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="f5dfd-132">ユーザー定義型の宣言は、キーワード `newtype`で構成され、その後にユーザー定義型の名前、`=`、有効な型指定、および終端のセミコロンが続きます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="f5dfd-133">例えば次が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="f5dfd-134">各 Q # ソースファイルは、任意の数のユーザー定義型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="f5dfd-135">型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="f5dfd-136">ユーザー定義型の間に循環依存関係を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="f5dfd-137">このため、Q # では再帰型を使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="f5dfd-138">操作の宣言</span><span class="sxs-lookup"><span data-stu-id="f5dfd-138">Operation Declarations</span></span>

<span data-ttu-id="f5dfd-139">操作は Q # の中核であり、他の言語の関数とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="f5dfd-140">各 Q # ソースファイルでは、任意の数の操作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="f5dfd-141">操作名は名前空間内で一意である必要があり、型および関数名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="f5dfd-142">操作の宣言は、キーワード `operation`、その後に操作の名前であるシンボル、操作の引数を定義する型指定された識別子のタプル、コロン `:`、操作の結果の型を記述する型の注釈で構成されます。必要に応じて、操作特性、左中かっこ `{`、操作宣言の本体、および最後の右中かっこ `}`を含む注釈。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="f5dfd-143">操作宣言の本体は、既定の実装または特殊化のリストのいずれかで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="f5dfd-144">既定の本体の特殊化の実装のみを明示的に指定する必要がある場合は、既定の実装を宣言内で直接指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="f5dfd-145">この場合、宣言の操作特性を持つ注釈を使用すると、コンパイラが既定の実装に基づいて他の特殊化を自動生成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="f5dfd-146">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="f5dfd-147">操作特性は、宣言された操作に適用できる機能の種類と、その効果を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="f5dfd-148">操作で、 *adjointed*または*制御*されている場合の操作の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="f5dfd-149">これらの特殊化の存在は、操作シグネチャの一部として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="f5dfd-150">そのような暗黙的に宣言された各特殊化の対応する実装が、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="f5dfd-151">上の例では、adjoint、制御された、および制御された adjoint 特殊化がコンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="f5dfd-152">実装がコンパイラによって生成されない場合は、明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="f5dfd-153">このような明示的な特殊化宣言は、特定の特殊化を構築する方法を明確にする適切なジェネレーションディレクティブ、またはユーザー定義の実装で構成できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="f5dfd-154">たとえば、上記の `PrepareEntangledPair` のコードは、明示的な特殊化宣言を含む次のコードと同じです。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="f5dfd-155">キーワード `auto` は、特殊化された実装を生成する方法をコンパイラが決定する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="f5dfd-156">より正確な生成ディレクティブではなく、特定の特殊化の実装をコンパイラが生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="f5dfd-157">上の例では、`adjoint invert;` は、本体の実装を反転することによって adjoint の特殊化が生成されることを示し、`controlled adjoint invert;` は、の指定された実装を反転することによって、制御された adjoint 特殊化が生成されることを示します。制御された特殊化。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="f5dfd-158">`Adjoint` または `Controlled` ファンクタのアプリケーションをサポートする操作の場合、その戻り値の型を必ず `Unit`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="f5dfd-159">明示的特殊化の宣言</span><span class="sxs-lookup"><span data-stu-id="f5dfd-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="f5dfd-160">Q # 操作には、次の明示的特殊化宣言を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="f5dfd-161">`body` 特殊化は、動作が適用されていない操作の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="f5dfd-162">`adjoint` 特殊化は、`Adjoint` のファンクタが適用された操作の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="f5dfd-163">`controlled` 特殊化は、`Controlled` のファンクタが適用された操作の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="f5dfd-164">`controlled adjoint` 特殊化は、`Adjoint` と `Controlled` の両方のファンクターが適用された操作の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="f5dfd-165">この特殊化は、2つの commute があるため、`adjoint controlled`という名前にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="f5dfd-166">操作の特殊化は、特殊化タグ (例: `body`、`adjoint`など) で構成され、その後に次のいずれかが続きます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="f5dfd-167">明示的な宣言。以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="f5dfd-168">特殊化を生成する方法をコンパイラに指示するディレクティブ。次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="f5dfd-169">`intrinsic`。ターゲットコンピューターによって特殊化が提供されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="f5dfd-170">`distribute`。 `controlled` および `controlled adjoint` の特殊化と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="f5dfd-171">`controlled`と共に使用すると、コンパイラは `body`内のすべての操作に `Controlled` を適用することによって、特殊化を計算する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="f5dfd-172">`controlled adjoint`と共に使用する場合、`adjoint` 特殊化のすべての操作に `Controlled` を適用することによって、コンパイラが特殊化を計算する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="f5dfd-173">`invert`は、コンパイラが `body`を反転させることによって `adjoint` 特殊化を計算する必要があることを示します。つまり、操作の順序を逆にして、それぞれに adjoint を適用します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="f5dfd-174">`adjoint controlled`と共に使用すると、コンパイラは特殊化 `controlled` を反転させることにより、特殊化を計算する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="f5dfd-175">`self`、adjoint の特殊化が `body` 特殊化と同じであることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="f5dfd-176">これは、`adjoint` と `adjoint controlled` 特殊化に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="f5dfd-177">`adjoint controlled`の場合、`self` は `adjoint controlled` 特殊化が `controlled` 特殊化と同じであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="f5dfd-178">`auto`、コンパイラが適切なディレクティブを選択して適用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="f5dfd-179">`auto` は、`body` 特殊化には使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="f5dfd-180">ディレクティブと `auto` すべてには、末尾にセミコロン `;`を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="f5dfd-181">`body` の明示的な宣言が指定されている場合、`auto` ディレクティブは次のジェネレーションディレクティブに解決されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="f5dfd-182">`adjoint` 特殊化は、ディレクティブ `invert`に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="f5dfd-183">`controlled` 特殊化は、ディレクティブ `distribute`に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="f5dfd-184">`controlled` の明示的な宣言が指定されていても `adjoint`にはない場合は、ディレクティブ `invert` に従って `adjoint controlled` 特殊化が生成され、それ以外の場合は `distribute` ます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="f5dfd-185">操作が自己 adjoint の場合、コンパイラが最適化のためにその情報を使用できるようにするには、明示的に adjoint または制御されている adjoint の特殊化を生成ディレクティブ `self` 経由で指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="f5dfd-186">ユーザー定義の実装を含む特殊化宣言は、引数の組の後に、特殊化を実装する Q # コードを持つステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="f5dfd-187">引数リストでは、`...` を使用して、操作全体に対して宣言された引数を表します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="f5dfd-188">`body` と `adjoint`では、引数リストは常に `(...)`である必要があります。`controlled` と `adjoint controlled`の場合、引数リストは、コントロールの qubits の配列を表すシンボルで、その後にかっこで囲まれた `...`が続く必要があります。たとえば、`(controls,...)`のようにします。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="f5dfd-189">既定の本体以外の1つ以上の特殊化を明示的に宣言する必要がある場合は、既定の本体の実装を適切な特殊化宣言にもラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="f5dfd-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="f5dfd-190">Adjoint</span></span>

<span data-ttu-id="f5dfd-191">操作の adjoint は、操作の複雑な共役の置換を実装する方法を指定します。つまり、"逆順で実行する" 操作がどのように動作するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="f5dfd-192">Adjoint なしで操作を指定することはできます。たとえば、測定操作は反転できるではないため、adjoint を持ちません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="f5dfd-193">操作は、宣言に adjoint 特殊化の暗黙的または明示的な宣言が含まれている場合、`Adjoint` のファンクタをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="f5dfd-194">明示的に宣言された制御済み adjoint 特殊化は、adjoint の特殊化が存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="f5dfd-195">操作の場合、本文に繰り返しループのループ、set ステートメント、測定、return ステートメント、または `Adjoint` ファンクタをサポートしていないその他の操作への呼び出しが含まれています。この場合、`invert` に続く adjoint 特殊化が自動生成され `auto` ディレクティブは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="f5dfd-196">た</span><span class="sxs-lookup"><span data-stu-id="f5dfd-196">Controlled</span></span>

<span data-ttu-id="f5dfd-197">操作の制御されたバージョンは、クォンタムによって制御されるバージョンの操作を実装する方法を指定します。つまり、クォンタムレジスタの状態に対して条件を適用した場合、操作がどのように動作するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="f5dfd-198">詳細な説明については、「[制御](xref:microsoft.quantum.language.type-model#controlled)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="f5dfd-199">制御されていないバージョンの操作を指定することはできます。たとえば、測定操作は制御できないので、制御されたバージョンではありません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="f5dfd-200">操作は、制御された特殊化の暗黙的または明示的な宣言が宣言に含まれている場合にのみ、`Controlled` ファンクタをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="f5dfd-201">明示的に宣言された制御済み adjoint 特殊化は、制御された特殊化が存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="f5dfd-202">`Controlled` ファンクタをサポートしていないその他の操作への呼び出しが本文に含まれている操作の場合、`distribute` または `auto` ディレクティブの後に制御される特殊化を自動生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="f5dfd-203">制御された Adjoint</span><span class="sxs-lookup"><span data-stu-id="f5dfd-203">Controlled Adjoint</span></span>

<span data-ttu-id="f5dfd-204">操作の制御された adjoint バージョンは、操作のクォンタム制御バージョンを実装する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="f5dfd-205">制御されていない adjoint バージョンを持つ操作を指定することはできます。たとえば、測定操作には制御できない、または反転できるではないため、adjoint バージョンは制御されません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="f5dfd-206">操作の制御された adjoint 特殊化は、adjoint と制御対象の両方の特殊化が存在する場合にのみ存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="f5dfd-207">この場合、制御された adjoint 特殊化の存在が推論され、明示的に定義された実装がない場合は、コンパイラによって適切な特殊化が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="f5dfd-208">制御された adjoint バージョンを持たない他の操作への呼び出しが本文に含まれている操作の場合、`distribute` または `auto` ディレクティブに `invert`続く adjoint の特殊化を自動生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="f5dfd-209">例</span><span class="sxs-lookup"><span data-stu-id="f5dfd-209">Examples</span></span>

<span data-ttu-id="f5dfd-210">操作の宣言は、次のように単純なものにすることができます。これにより、プリミティブな P# li X 操作が定義されます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="f5dfd-211">次の例では、テレポート操作を定義しています。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="f5dfd-212">関数の宣言</span><span class="sxs-lookup"><span data-stu-id="f5dfd-212">Function Declarations</span></span>

<span data-ttu-id="f5dfd-213">関数は、Q # の純粋な古典ルーチンです。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="f5dfd-214">各 Q # ソースファイルでは、任意の数の関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="f5dfd-215">関数宣言は、キーワード `function`、その後に関数の名前、型指定された識別子の組、関数の戻り値の型を記述する型の注釈、およびの実装を記述するステートメントブロックで構成されます。プロシージャ.</span><span class="sxs-lookup"><span data-stu-id="f5dfd-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="f5dfd-216">関数を定義するステートメントブロックは `{` で囲み、他のステートメントブロックと同様に `}` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="f5dfd-217">関数名は名前空間内で一意である必要があり、操作と型名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="f5dfd-218">関数は、qubits の割り当てや借用、操作の呼び出しを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="f5dfd-219">操作を部分的に適用するか、操作の型指定された値をラップすることは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="f5dfd-220">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5dfd-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
