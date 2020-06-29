---
title: Q# の型
description: 'Q # プログラミング言語で使用されるさまざまな型について説明します。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415287"
---
# <a name="types-in-q"></a><span data-ttu-id="01b7d-103">Q# の型</span><span class="sxs-lookup"><span data-stu-id="01b7d-103">Types in Q#</span></span>

<span data-ttu-id="01b7d-104">この記事では、Q # 型モデルと、型を指定して操作するための構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="01b7d-105">これらの型の式を作成および操作する方法の詳細については、「[型式](xref:microsoft.quantum.guide.expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="01b7d-106">Q # は*厳密に型指定*された言語であるため、これらの型を慎重に使用することは、コンパイル時に q # プログラムに対する強力な保証をコンパイラが提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="01b7d-107">可能な限り強力な保証を提供するには、Q # の型間の変換を、その変換を表す関数の呼び出しを使用して明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="01b7d-108">Q # は、名前空間の一部として、このようなさまざまな機能を提供し <xref:microsoft.quantum.convert> ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="01b7d-109">一方、互換性のある型へのアップキャストは暗黙的に行われます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="01b7d-110">Q # には、直接使用されるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="01b7d-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="01b7d-111">この記事の残りの部分では、それぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="01b7d-112">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="01b7d-112">Primitive Types</span></span>

<span data-ttu-id="01b7d-113">Q # 言語には、次の*プリミティブ型*が用意されています。これらはすべて、q # プログラムで直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="01b7d-114">これらのプリミティブ型を使用して、新しい型を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="01b7d-115">この `Int` 型は、64ビット符号付き整数 (、、など) を表し `2` `107` `-5` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="01b7d-116">型は、、、など、 `BigInt` 任意のサイズの符号付き整数を表し `2L` `107L` `-5L` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="01b7d-117">この型は .NET に基づいています。<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="01b7d-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="01b7d-118">各種.</span><span class="sxs-lookup"><span data-stu-id="01b7d-118">type.</span></span>

- <span data-ttu-id="01b7d-119">型は、、、など `Double` の倍精度浮動小数点数を表し `0.0` `-1.3` `4e-7` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="01b7d-120">型は、 `Bool` またはのいずれかのブール値を表し `true` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="01b7d-121">この `Range` 型は、によって示される整数のシーケンスを表し `start..step..stop` ます。これは、ステップが省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="01b7d-122">たとえば、は `start .. stop` に対応 `start..1..stop` し、は `1..2..7` シーケンス $ \{ 1、3、5、7 $ を表し \} ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="01b7d-123">この `String` 型は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="01b7d-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="01b7d-124">エラーまたは診断イベントが発生した場合に、この種類を使用して、 `string` 従来のホストにメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="01b7d-125">`Unit`型は、値を1つだけ持つことができ `()` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="01b7d-126">この型を使用して、Q # 関数または操作が情報を返さないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="01b7d-127">この `Qubit` 型は、クォンタムビットまたは qubit を表します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="01b7d-128">`Qubit`はユーザーに対して非透過的です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="01b7d-129">他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。</span><span class="sxs-lookup"><span data-stu-id="01b7d-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="01b7d-130">最終的には、 `Qubit` クォンタムプロセッサ (またはクォンタムシミュレーター) で組み込み命令を呼び出すことによって、に対するアクションを実装します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="01b7d-131">この `Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="01b7d-132">この型を使用して、回転の基本操作を表し、測定対象の観測対象を指定します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="01b7d-133">これは `PauliI` 、 `PauliX` `PauliY` `PauliZ` 型の定数である、、、およびの4つの値を持つ列挙型 `Pauli` です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="01b7d-134">型は、 `Result` 測定の結果を表します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="01b7d-135">これは、 `One` `Zero` 型の定数であるとの2つの値を持つ列挙 `Result` 型です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="01b7d-136">`Zero`+ 1 eigenvalue が測定されたことを示します。`One`-1 eigenvalue が測定されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="01b7d-137">、、、、、、、およびの各定数 `true` `false` は、 `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # で予約されているすべての記号です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="01b7d-138">配列型</span><span class="sxs-lookup"><span data-stu-id="01b7d-138">Array Types</span></span>

* <span data-ttu-id="01b7d-139">有効な Q # 型については、その型の値の配列を表す型があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="01b7d-140">たとえば、とは、 `Qubit[]` `(Bool, Pauli)[]` `Qubit` 値と組値の配列を表し `(Bool, Pauli)` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="01b7d-141">配列の配列も有効です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-141">An array of arrays is also valid.</span></span> <span data-ttu-id="01b7d-142">前の例を展開すると、配列の配列 `(Bool, Pauli)` が示され `(Bool, Pauli)[][]` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="01b7d-143">この例は、 `(Bool, Pauli)[][]` 四角形の2次元配列ではなく、配列のジャグ配列を表しています。</span><span class="sxs-lookup"><span data-stu-id="01b7d-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="01b7d-144">Q # は、四角形多次元配列をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="01b7d-145">配列の値は、のように、配列の要素を角かっこで囲むことによって、Q # のソースコードで記述でき `[PauliI, PauliX, PauliY, PauliZ]` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="01b7d-146">配列内のすべての項目の共通基本型によって、配列リテラルの型が決定されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="01b7d-147">そのため、共通の基本型を持たない要素を含む配列を構築すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="01b7d-148">例については、「[呼び出し許容の配列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="01b7d-149">作成された配列の要素は変更できません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="01b7d-150">変更された配列を作成するには、[更新と再割り当てのステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)、または[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="01b7d-151">または、キーワードを使用して、配列のサイズから配列を作成することもでき `new` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="01b7d-152">`Length`配列からの要素の数をとして取得するには、core 関数を使用し `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="01b7d-153">配列は、配列の要素のサブセットを含む単一の要素または新しい配列を取得するために、添字にすることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="01b7d-154">配列の添字は0から始まり、型または型である必要があり `Int` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="01b7d-155">タプル型</span><span class="sxs-lookup"><span data-stu-id="01b7d-155">Tuple Types</span></span>

<span data-ttu-id="01b7d-156">タプルは、1つの値に値をまとめて収集し、それらを簡単に渡すことができるようにするために、Q # 全体で使用される強力な概念です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="01b7d-157">特に、組表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、1つの出力のみを返すことを表現できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="01b7d-158">0個以上の異なる型 `T0` ( `T1` ,...) を指定する `Tn` と、新しい*タプル型*をとして表すことができます。 `(T0, T1, ..., Tn)`</span><span class="sxs-lookup"><span data-stu-id="01b7d-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="01b7d-159">新しいタプル型を構築するために使用される型は、のように、それ自体をタプルにすることができ `(Int, (Qubit, Qubit))` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="01b7d-160">ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="01b7d-161">新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。</span><span class="sxs-lookup"><span data-stu-id="01b7d-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="01b7d-162">たとえば、 `(3, false)` は、型がタプル型であるタプルです `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="01b7d-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="01b7d-163">組の配列、配列の組、サブタプルの組などを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="01b7d-164">Q # 0.3 の場合、 `Unit` は空のタプルの*型*の名前です。 `()` は空のタプルの*値*に使用されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="01b7d-165">タプルインスタンスは変更できません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="01b7d-166">Q # には、作成されたタプルの内容を変更する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="01b7d-167">シングルトンタプルの等価性</span><span class="sxs-lookup"><span data-stu-id="01b7d-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="01b7d-168">またはなど、シングルトン (単一要素) の組を作成することができ `('T1)` `(5)` `([1,2,3])` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="01b7d-169">ただし、Q # は、シングルトンタプルを、囲まれた型の値と等価のものとして扱います。</span><span class="sxs-lookup"><span data-stu-id="01b7d-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="01b7d-170">つまり、との間、との間、 `5` `(5)` `5` `(((5)))` または `(5, (6))` と `(5, 6)` の間に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="01b7d-171">書き込みの場合と同じように記述できます。 `(5)+3` `5+3` 両方の式がに評価され `8` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="01b7d-172">この等価性は、代入式や式など、すべての目的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="01b7d-173">任意の式を指定すると、かっこで囲まれた同じ式が同じ型の式になります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="01b7d-174">たとえば、 `(7)` は型の式、は型の式、は `Int` `([1,2,3])` `Int[]` `((1,2))` 型の `(Int, Int)` 式です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="01b7d-175">特に、これは、1つの引数を受け取るか、単一の値を返すとして、入力タプルまたは出力タプル型に1つのフィールドがある操作または関数を表示できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="01b7d-176">このプロパティは、_シングルトンタプルの等価性_と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="01b7d-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="01b7d-177">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="01b7d-177">User-Defined Types</span></span>

<span data-ttu-id="01b7d-178">ユーザー定義型の宣言は、キーワード、 `newtype` その後にユーザー定義型の名前、 `=` 有効な型指定、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="01b7d-179">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="01b7d-180">各 Q # ソースファイルは、任意の数のユーザー定義型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="01b7d-181">型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="01b7d-182">基本型が同一であっても、ユーザー定義型は区別されません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="01b7d-183">特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="01b7d-184">名前付き項目と匿名項目</span><span class="sxs-lookup"><span data-stu-id="01b7d-184">Named vs. anonymous items</span></span>

<span data-ttu-id="01b7d-185">Q # ファイルでは、任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="01b7d-186">任意のタプル型では、ステートメントを使用して、 `T` のサブタイプである新しいユーザー定義型を宣言でき `T` `newtype` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="01b7d-187">たとえば、 @"microsoft.quantum.math" 名前空間では、複合数値はユーザー定義型として定義されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="01b7d-188">このステートメントは、型の2つの匿名項目を持つ新しい型を作成し `Double` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="01b7d-189">ユーザー定義型では、匿名項目以外に、Q # バージョン0.7 以降の*名前付き項目*もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="01b7d-190">たとえば、 `Re` 複素数の実数部と虚数部を表す double 型の項目に、という名前を指定でき `Im` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="01b7d-191">ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="01b7d-192">さらに、内部項目にもという名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="01b7d-193">次の例に示すように、型には `Nested` 基になる型があり、型 `(Double, (Int, String))` の項目だけ `Int` が名前付きで、他のすべての項目は匿名になります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="01b7d-194">名前付き項目には、*アクセス演算子*を使用して直接アクセスできるという利点があり `::` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="01b7d-195">潜在的に複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義することの大きな利点は、特定の値の意図を文書化できることです。</span><span class="sxs-lookup"><span data-stu-id="01b7d-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="01b7d-196">の例に戻る `Complex` と、ユーザー定義型として2d 極座標座標を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="01b7d-197">との両方に基になる型がある場合でも、 `Complex` `Polar` `(Double, Double)` 2 つの型は Q # で完全には互換性がないため、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="01b7d-198">ラップ解除演算子を使用した匿名項目へのアクセス</span><span class="sxs-lookup"><span data-stu-id="01b7d-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="01b7d-199">匿名項目にアクセスするには、まず、後置演算子を使用して、ラップされた値を抽出し `!` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="01b7d-200">"ラップ解除" 演算子を使用 `!` すると、ユーザー定義型に含まれる値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="01b7d-201">このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。</span><span class="sxs-lookup"><span data-stu-id="01b7d-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="01b7d-202">単一のラップ解除演算子は、ラップの1つのレイヤーをラップ解除します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="01b7d-203">多重ラップされた値にアクセスするには、複数のラップ解除演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="01b7d-204">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="01b7d-205">ラップ解除演算子の詳細については、「 [Q # の型式](xref:microsoft.quantum.guide.expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="01b7d-206">ユーザー定義型の値の作成</span><span class="sxs-lookup"><span data-stu-id="01b7d-206">Creating values of user-defined types</span></span>

<span data-ttu-id="01b7d-207">対応する型コンストラクターを呼び出すことによって、ユーザー定義型の値を作成します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="01b7d-208">または、[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="01b7d-209">配列の場合と同様に、コピーと更新の式では、指定した名前付き項目を除き、元の式のすべての項目値がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="01b7d-210">これらの例外の場合、これらの項目の値は、式の右辺に定義されている値になります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="01b7d-211">配列項目に使用できるその他の言語構成要素 (たとえば、 [update および-再割り当てステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)) は、ユーザー定義型の名前付き項目にも存在します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="01b7d-212">ユーザー定義型は、他の型を使用する場所であればどこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="01b7d-213">特に、ユーザー定義型の配列を定義し、タプル型の要素としてユーザー定義型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="01b7d-214">再帰型構造を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="01b7d-215">つまり、ユーザー定義型を定義する型を、ユーザー定義型の要素を含むタプル型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="01b7d-216">一般に、ユーザー定義型は相互に循環依存関係がない場合があるため、次の型定義のセットは無効になります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="01b7d-217">操作と関数の型</span><span class="sxs-lookup"><span data-stu-id="01b7d-217">Operation and Function Types</span></span>

<span data-ttu-id="01b7d-218">次の型 `'Tinput` が `'Tresult` あります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="01b7d-219">`('Tinput => 'Tresult)`は、任意の*操作*の基本型です。たとえば、のように `((Qubit, Pauli) => Result)` なります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="01b7d-220">`('Tinput -> 'Tresult)`は、任意の*関数*の基本型です。たとえば、のように `(Int -> Int)` なります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="01b7d-221">これらは呼び出し可能の*シグネチャ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="01b7d-222">すべての Q # 呼び出しが、1つの値を入力として受け取り、1つの値を出力として返します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="01b7d-223">入力値と出力値の両方に組を使用できます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="01b7d-224">結果がない呼び出しの可能性がある場合は、を返し `Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="01b7d-225">入力がない callables は、空のタプルを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="01b7d-226">ファンクター</span><span class="sxs-lookup"><span data-stu-id="01b7d-226">Functors</span></span>

<span data-ttu-id="01b7d-227">*関数*型は、シグネチャによって完全に指定されます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="01b7d-228">たとえば、角度のサインを計算する関数には型があり `(Double -> Double)` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="01b7d-229">*操作に*は、操作の種類の一部として表現されるいくつかの追加の特性があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="01b7d-230">このような特性*には、操作でサポート*される機能に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="01b7d-231">たとえば、操作の実行が他の qubits の状態に依存している場合は、ファンクタをサポートする必要があり `Controlled` ます。操作に逆のがある場合は、ファンクタをサポートする必要があり `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="01b7d-232">この記事では、操作シグネチャの変更についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="01b7d-233">関数と操作の詳細については、「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="01b7d-234">`Controlled`操作の種類でおよび/またはファンクタのサポートを要求するには、 `Adjoint` 対応する特性を示す注釈を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="01b7d-235">注釈 `is Ctl` (たとえば、) は、 `(Qubit => Unit is Ctl)` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="01b7d-236">つまり、その実行は、別の qubit または qubit の状態に依存します。</span><span class="sxs-lookup"><span data-stu-id="01b7d-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="01b7d-237">同様に、注釈は、操作に adjoint があることを示します。つまり、 `is Adj` 操作を連続して適用した後、その状態を状態に変更せずに状態を維持する "逆" にすることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="01b7d-238">その型の操作がとのファンクタの両方をサポートしていることを要求する場合は、 `Adjoint` `Controlled` これをとして表現でき `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="01b7d-239">たとえば、組み込みの P# li <xref:microsoft.quantum.intrinsic.x> 操作には型があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="01b7d-240">すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="01b7d-241">型パラメーターの関数と操作</span><span class="sxs-lookup"><span data-stu-id="01b7d-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="01b7d-242">呼び出し可能な型には、*型パラメーター*を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="01b7d-243">1つの引用符で始まる記号を使用して、型パラメーターを指定します。たとえば、 `'A` は有効な型パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="01b7d-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="01b7d-244">型パラメーター化された呼び出しを定義する方法の詳細と詳細については、「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="01b7d-245">1つのシグネチャで、型パラメーターが複数回出現する場合があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="01b7d-246">たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャを持ち `(('A[], 'A->'A) -> 'A[])` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="01b7d-247">同様に、2つの操作の構成を返す関数には、シグネチャがあり `((('A=>'B), ('B=>'C)) -> ('A=>'C))` ます。</span><span class="sxs-lookup"><span data-stu-id="01b7d-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="01b7d-248">型パラメーターの呼び出し可能な呼び出しを呼び出す場合は、同じ型パラメーターを持つすべての引数が同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b7d-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="01b7d-249">Q # には、ユーザーが型パラメーターの代わりに使用できる型を制約する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="01b7d-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01b7d-250">次のステップ</span><span class="sxs-lookup"><span data-stu-id="01b7d-250">Next steps</span></span>

<span data-ttu-id="01b7d-251">これで、Q # 言語を構成するすべての型がわかりました。次は、これらのさまざまな型の式を作成および操作する方法については、「 [q # の型式](xref:microsoft.quantum.guide.expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b7d-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
