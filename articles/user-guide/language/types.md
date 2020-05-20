---
title: Q# の型
description: 'Q # プログラミング言語で使用されるさまざまな型について説明します。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609143"
---
# <a name="types-in-q"></a><span data-ttu-id="0ee4e-103">Q# の型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-103">Types in Q#</span></span>

<span data-ttu-id="0ee4e-104">このページでは、Q # 型モデルをレイアウトし、型を指定して操作するための構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="0ee4e-105">次のページ「[型の式](xref:microsoft.quantum.guide.expressions)」では、これらの型の式を作成および操作する方法について詳しく説明しています。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="0ee4e-106">Q # は*厳密に型指定*された言語であるため、これらの型を慎重に使用することは、コンパイル時に q # プログラムに対する強力な保証をコンパイラが提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="0ee4e-107">最も強力な保証を提供するために、Q # の型間の変換は、その変換を表す関数の呼び出しを使用して明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="0ee4e-108">このような関数は、名前空間の一部として提供されてい <xref:microsoft.quantum.convert> ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="0ee4e-109">一方、互換性のある型へのアップキャストは暗黙的に行われます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="0ee4e-110">Q # には、直接使用できるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="0ee4e-111">各項目については、このセクションの残りの部分で説明します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="0ee4e-112">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-112">Primitive Types</span></span>

<span data-ttu-id="0ee4e-113">Q # 言語には、他の型を構築できるいくつかの*プリミティブ型*が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="0ee4e-114">この `Int` 型は、64ビットの符号付き整数を表します。例: `2` 、 `107` 、 `-5` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="0ee4e-115">型は、 `BigInt` 任意のサイズの符号付き整数 (、など) を表します `2L` `107L` `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="0ee4e-116">この型は .NET に基づいています。<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="0ee4e-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="0ee4e-117">各種.</span><span class="sxs-lookup"><span data-stu-id="0ee4e-117">type.</span></span>
- <span data-ttu-id="0ee4e-118">型は、 `Double` 倍精度浮動小数点数を表します。例: `0.0` 、 `-1.3` 、 `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="0ee4e-119">型は、 `Bool` またはのいずれかのブール値を表し `true` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="0ee4e-120">この `Range` 型は、によって示される整数のシーケンスを表し `start..step..stop` ます。これは、ステップが省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="0ee4e-121">これは `start .. stop` に対応 `start..1..stop` します。例: は、 `1..2..7` シーケンス $ \{ 1、3、5、7 $ を表し \} ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="0ee4e-122">この `String` 型は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="0ee4e-123">この型は、エラーまたは診断イベントが発生した場合に、従来のホストにメッセージを報告するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="0ee4e-124">`Unit`型は、1つの値のみを許可する型です `()` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="0ee4e-125">この型は、Q # 関数または操作が情報を返さないことを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="0ee4e-126">この `Qubit` 型は、クォンタムビットまたは qubit を表します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="0ee4e-127">`Qubit`はユーザーに対して非透過的です。他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="0ee4e-128">最終的に、に対するアクション `Qubit` は、クォンタムプロセッサ (またはシミュレーション) で組み込み命令を呼び出すことによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="0ee4e-129">この `Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="0ee4e-130">この型は、回転の基本操作を表し、測定対象の観測対象を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="0ee4e-131">これは `PauliI` 、 `PauliX` `PauliY` `PauliZ` 型の定数である、、、およびの4つの値を持つ列挙型 `Pauli` です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="0ee4e-132">型は、 `Result` 測定の結果を表します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="0ee4e-133">これは、 `One` `Zero` 型の定数であるとという2つの値を持つ列挙型 `Result` です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="0ee4e-134">`Zero`+ 1 eigenvalue が測定されたことを示します。`One`-1 eigenvalue を示します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="0ee4e-135">、、、、、、、およびの各定数 `true` `false` は、 `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # で予約されているすべての記号です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="0ee4e-136">配列型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-136">Array Types</span></span>

<span data-ttu-id="0ee4e-137">有効な Q # 型が指定され `'T` ている場合、型の値の配列を表す型があり `'T` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="0ee4e-138">この配列型は、やなど、として表され `'T[]` `Qubit[]` `Int[][]` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="0ee4e-139">たとえば、整数のコレクションが示され、 `Int[]` 値の配列の配列が `(Bool, Pauli)` 示され `(Bool, Pauli)[][]` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="0ee4e-140">2番目の例では、これは、四角形の2次元配列ではなく、配列のジャグ配列を表すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="0ee4e-141">Q # では、四角形多次元配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="0ee4e-142">配列の値は、のように、配列の要素を角かっこで囲むことによって、Q # のソースコードで記述でき `[PauliI, PauliX, PauliY, PauliZ]` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="0ee4e-143">配列リテラルの型は、配列内のすべての項目の共通基本型によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="0ee4e-144">配列の要素は、配列の作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="0ee4e-145">[更新と再割り当てのステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)、または[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、変更された配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="0ee4e-146">または、キーワードを使用して、配列のサイズから配列を作成することもでき `new` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="0ee4e-147">どちらの場合も、配列が構築されると、コア関数を `Length` 使用して要素の数をとして取得でき `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="0ee4e-148">配列は、角かっこを使用して下付き文字にすることができます。また、添字は型または型のいずれかで、 `Int` `Range` 1 つの要素または配列の要素のサブセットを含む新しい配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="0ee4e-149">配列の添字は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="0ee4e-150">タプル型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-150">Tuple Types</span></span>

<span data-ttu-id="0ee4e-151">0個以上の異なる型を指定した場合は、 `T0` `T1` `Tn` 新しい*タプル型*をとして表すことができます `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="0ee4e-152">新しいタプル型を構築するために使用される型は、のように、それ自体をタプルにすることができ `(Int, (Qubit, Qubit))` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="0ee4e-153">ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="0ee4e-154">新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="0ee4e-155">たとえば、 `(3, false)` は、型がタプル型であるタプルです `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="0ee4e-156">組、配列の組、サブタプルの組などの配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="0ee4e-157">Q # 0.3 の場合、 `Unit` は空のタプルの*型*の名前です。 `()` は空のタプル*値*に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="0ee4e-158">タプルインスタンスは変更できません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="0ee4e-159">Q # には、作成されたタプルの内容を変更する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="0ee4e-160">タプルは、1つの値に値をまとめて収集し、それらを簡単に渡すことができるようにするために、Q # 全体で使用される強力な概念です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="0ee4e-161">特に、タプル表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、ただ1つの出力を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="0ee4e-162">シングルトンタプルの等価性</span><span class="sxs-lookup"><span data-stu-id="0ee4e-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="0ee4e-163">またはのように、シングルトン (単一要素) の組を作成することもでき `('T1)` `(5)` `([1,2,3])` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="0ee4e-164">ただし、Q # は、シングルトンタプルを、囲まれた型の値と完全に等価なものとして扱います。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="0ee4e-165">つまり、との間、との間、 `5` `(5)` `5` `(((5)))` または `(5, (6))` と `(5, 6)` の間に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="0ee4e-166">書き込み用に書き込みを行うのと同じです `(5)+3` `5+3` 。両方の式がに評価され `8` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="0ee4e-167">この等価性は、代入式や式など、すべての目的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="0ee4e-168">任意の式を指定すると、かっこで囲まれた同じ式が同じ型の式になります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="0ee4e-169">たとえば、 `(7)` は式、は `Int` `([1,2,3])` の配列型の式、は型の式です `Int` `((1,2))` `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="0ee4e-170">特に、これは、入力タプルまたは出力タプル型が1つのフィールドを持つ演算または関数は、1つの引数を受け取るか、単一の値を返すと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="0ee4e-171">このプロパティは、_シングルトンタプルの等価性_と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="0ee4e-172">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-172">User-Defined Types</span></span>

<span data-ttu-id="0ee4e-173">ユーザー定義型の宣言は、キーワード、 `newtype` その後にユーザー定義型の名前、 `=` 有効な型指定、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="0ee4e-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="0ee4e-175">各 Q # ソースファイルは、任意の数のユーザー定義型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="0ee4e-176">型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="0ee4e-177">基本型が同一の場合でも、ユーザー定義型は区別されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="0ee4e-178">特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="0ee4e-179">名前付き項目と匿名項目</span><span class="sxs-lookup"><span data-stu-id="0ee4e-179">Named vs. anonymous items</span></span>

<span data-ttu-id="0ee4e-180">Q # ファイルでは、任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="0ee4e-181">任意のタプル型では、ステートメントを使用して、 `T` のサブタイプである新しいユーザー定義型を宣言でき `T` `newtype` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="0ee4e-182">たとえば、 @"microsoft.quantum.math" 名前空間では、複素数はユーザー定義型として定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="0ee4e-183">このステートメントは、型の2つの匿名項目を持つ新しい型を作成し `Double` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="0ee4e-184">ユーザー定義型では、匿名項目以外に、Q # バージョン0.7 以降の*名前付き項目*もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="0ee4e-185">たとえば、 `Re` 複素数の実数部と虚数部を表す double 型の to 項目という名前を付けることができ `Im` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="0ee4e-186">ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="0ee4e-187">さらに、内部項目にもという名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="0ee4e-188">たとえば、 `Nested` 次に定義されている型には基になる型があり、その中に `(Double, (Int, String))` は型の項目だけが指定され、 `Int` 他のすべての項目は匿名になります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="0ee4e-189">名前付き項目には、*アクセス演算子*を使用して直接アクセスできるという利点があり `::` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="0ee4e-190">複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義する大きな利点の1つは、特定の値の意図を文書化できることです。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="0ee4e-191">の例に戻る `Complex` と、ユーザー定義型として2d 極座標座標を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="0ee4e-192">との両方 `Complex` に基になる型がある場合でも、 `Polar` `(Double, Double)` 2 つの型は完全には互換性がありません。これにより、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="0ee4e-193">このように、ユーザー定義型は F # のレコードと同様のロールを持ちます。たとえば、</span><span class="sxs-lookup"><span data-stu-id="0ee4e-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="0ee4e-194">ラップ解除演算子を使用した匿名項目へのアクセス</span><span class="sxs-lookup"><span data-stu-id="0ee4e-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="0ee4e-195">一方、匿名の項目にアクセスするには、後置演算子を使用して、ラップされた値を最初に抽出する必要があり `!` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="0ee4e-196">"ラップ解除" 演算子を `!` 使用すると、ユーザー定義型に含まれる値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="0ee4e-197">このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="0ee4e-198">ラップ解除演算子は、ラップのレイヤーを1つだけラップ解除します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="0ee4e-199">複数のラップ解除演算子は、乗算された値にアクセスするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="0ee4e-200">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-200">For instance:</span></span>

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

<span data-ttu-id="0ee4e-201">ラップ解除演算子の詳細については、 [「Q # の型式」](xref:microsoft.quantum.guide.expressions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="0ee4e-202">ユーザー定義型の値の作成</span><span class="sxs-lookup"><span data-stu-id="0ee4e-202">Creating values of user-defined types</span></span>

<span data-ttu-id="0ee4e-203">ユーザー定義型の値は、対応する型コンストラクターを呼び出すことによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="0ee4e-204">または、[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="0ee4e-205">配列の場合と同様に、このような式は、指定された名前付き項目を除き、元の式のすべての項目の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="0ee4e-206">これらの値は、式の右辺に定義されている値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="0ee4e-207">配列項目に使用できるその他の言語構成要素は[、たとえば、](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)ユーザー定義型の名前付き項目にも存在します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="0ee4e-208">ユーザー定義型は、他の型を使用できる場所であればどこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="0ee4e-209">特に、ユーザー定義型の配列を定義し、タプル型の要素としてユーザー定義型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="0ee4e-210">再帰型構造を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="0ee4e-211">つまり、ユーザー定義型を定義する型を、ユーザー定義型の要素を含むタプル型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="0ee4e-212">一般に、ユーザー定義型は相互に循環依存関係がない場合があるため、次の型定義のセットは無効になります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="0ee4e-213">操作と関数の型</span><span class="sxs-lookup"><span data-stu-id="0ee4e-213">Operation and Function Types</span></span>

<span data-ttu-id="0ee4e-214">呼び出し可能の基本型は、またはとして記述され `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` ます。ここで、との両方 `'Tinput` `'Tresult` が型です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="0ee4e-215">これらは呼び出し可能の*シグネチャ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="0ee4e-216">すべての Q # 呼び出しが、1つの値を入力として受け取り、1つの値を出力として返すと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="0ee4e-217">入力値と出力値は、どちらもタプルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="0ee4e-218">結果が返されない呼び出しの可能性があり `Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="0ee4e-219">入力がない callables は、空のタプルを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="0ee4e-220">最初の形式であるは、 `=>` 操作に使用されます。2番目の形式は、関数の場合はとです `->` 。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="0ee4e-221">たとえば、は、 `((Qubit, Pauli) => Result)` 可能な単一 qubit 測定演算の署名を表します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="0ee4e-222">*関数*型は、シグネチャによって完全に指定されます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="0ee4e-223">たとえば、角度のサインを計算する関数には型があり `(Double -> Double)` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="0ee4e-224">*操作---で*はなく、操作の種類の一部として表される特定の追加の特性を持つ関数---。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="0ee4e-225">このような特性には、操作が*サポートする機能*に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="0ee4e-226">たとえば、操作の実行を他の qubits の状態で条件指定できる場合は、ファンクタをサポートする必要があり `Controlled` ます。操作に逆のがある場合は、ファンクタをサポートする必要があり `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="0ee4e-227">関数と演算の詳細については、「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。ここでは、操作のシグネチャを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="0ee4e-228">操作の種類の and またはファンクタのサポートを必要とするために `Controlled` `Adjoint` 、対応する特性を示す注釈を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="0ee4e-229">注釈 (例:) は、操作が制御可能であることを `is Ctl` 示します。つまり `(Qubit => Unit is Ctl)` 、別の qubit または qubit の状態に対して実行条件が指定されている---です。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="0ee4e-230">同様に、は、 `is Adj` 操作に adjoint があることを示します。または、操作を連続して適用した後、その状態を状態に変更せずにそのまま状態を維持する "逆" にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="0ee4e-231">その型の操作がとの両方をサポートしていることを要求する場合は、 `Adjoint` `Controlled` これをとして表現でき `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="0ee4e-232">たとえば、組み込みの P# li <xref:microsoft.quantum.intrinsic.x> 操作には型があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="0ee4e-233">すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="0ee4e-234">型パラメーターの関数と操作</span><span class="sxs-lookup"><span data-stu-id="0ee4e-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="0ee4e-235">呼び出し可能な型には、型パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="0ee4e-236">型パラメーターは、1つの引用符で始まる記号で示されます。たとえば、 `'A` は有効な型パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="0ee4e-237">型パラメーター化された呼び出しを定義する方法の詳細については、 [Q # ページの操作と関数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="0ee4e-238">1つのシグネチャで、型パラメーターが複数回出現する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="0ee4e-239">たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャを持ち `(('A[], 'A->'A) -> 'A[])` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="0ee4e-240">同様に、2つの操作の構成を返す関数にはシグネチャがある場合があり `((('A=>'B), ('B=>'C)) -> ('A=>'C))` ます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="0ee4e-241">型パラメーターの呼び出し可能な呼び出しを呼び出すときは、同じ型パラメーターを持つすべての引数が同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="0ee4e-242">Q # には、型パラメーターに置き換えられる可能性のある型を制限する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="0ee4e-243">次の課題</span><span class="sxs-lookup"><span data-stu-id="0ee4e-243">What's Next?</span></span>
<span data-ttu-id="0ee4e-244">Q # 言語を構成するすべての型を確認したので、 [q # の式を入力](xref:microsoft.quantum.guide.expressions)して、これらのさまざまな型の式を作成および操作する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ee4e-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


