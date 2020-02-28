---
title: 'Q # データ型'
description: 'Q # プログラミング言語で使用されるさまざまな型について説明します。これには、組み込み型、配列、組、演算、関数、ユーザー定義型などが含まれます。'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904657"
---
# <a name="the-type-model"></a><span data-ttu-id="eb118-103">型モデル</span><span class="sxs-lookup"><span data-stu-id="eb118-103">The Type Model</span></span>

<span data-ttu-id="eb118-104">このセクションでは、Q # 型モデルについて説明し、型を指定して操作するための構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb118-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="eb118-105">Q # は*厳密に型指定*された言語であるため、これらの型を慎重に使用することは、コンパイル時に q # プログラムに対する強力な保証をコンパイラが提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb118-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="eb118-106">最も強力な保証を提供するために、Q # の型間の変換は、その変換を表す関数の呼び出しを使用して明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="eb118-107">このような関数は、<xref:microsoft.quantum.convert> 名前空間の一部として提供されています。</span><span class="sxs-lookup"><span data-stu-id="eb118-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="eb118-108">一方、互換性のある型へのアップキャストは暗黙的に行われます。</span><span class="sxs-lookup"><span data-stu-id="eb118-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="eb118-109">Q # には、直接使用できるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb118-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="eb118-110">各項目については、このセクションの残りの部分で説明します。</span><span class="sxs-lookup"><span data-stu-id="eb118-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="eb118-111">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="eb118-111">Primitive Types</span></span>

<span data-ttu-id="eb118-112">Q # 言語には、他の型を構築できるいくつかの*プリミティブ型*が用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb118-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="eb118-113">`Int` 型は、64ビット符号付き整数 (例: `2`、`107`、`-5`) を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="eb118-114">`BigInt` 型は、任意のサイズの符号付き整数 (`2L`、`107L`、`-5L`など) を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="eb118-115">この型は .NET <xref:System.Numerics.BigInteger> に基づいています。</span><span class="sxs-lookup"><span data-stu-id="eb118-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="eb118-116">各種.</span><span class="sxs-lookup"><span data-stu-id="eb118-116">type.</span></span>
- <span data-ttu-id="eb118-117">`Double` 型は、`0.0`、`-1.3`、`4e-7`などの倍精度浮動小数点数を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="eb118-118">`Bool` 型はブール値を表し、`true` または `false`を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="eb118-119">`Qubit` 型は、クォンタムビットまたは qubit を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="eb118-120">`Qubit`s はユーザーに対して非透過的です。他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。</span><span class="sxs-lookup"><span data-stu-id="eb118-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="eb118-121">最終的に、`Qubit`に対するアクションは、クォンタムプロセッサ (またはシミュレーション) で組み込み命令を呼び出すことによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="eb118-122">`Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="eb118-123">この型は、回転の基本操作を表し、測定対象の観測対象を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="eb118-124">これは、`PauliI`、`PauliX`、`PauliY`、および `PauliZ`の4つの値を持つ列挙型です。これは、型 `Pauli`の定数です。</span><span class="sxs-lookup"><span data-stu-id="eb118-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="eb118-125">`Result` 型は、測定の結果を表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="eb118-126">これは、`One` と `Zero`の2つの値を持つ列挙型であり、`Result`型の定数です。</span><span class="sxs-lookup"><span data-stu-id="eb118-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="eb118-127">`Zero` は、+ 1 eigenvalue が測定されたことを示します。`One` は、-1 eigenvalue を示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="eb118-128">`Range` 型は、`start..step..stop`によって示される整数のシーケンスを表します。これは、ステップがオプションであることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="eb118-129">この `start .. stop` は `start..1..stop`に対応します。たとえば、`1..2..7` は、$\{1、3、5、7\}$ というシーケンスを表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="eb118-130">`String` の種類は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="eb118-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="eb118-131">この型は、エラーまたは診断イベントが発生した場合に、従来のホストにメッセージを報告するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="eb118-132">`Unit` 型は、値を1つだけ `()`できる型です。</span><span class="sxs-lookup"><span data-stu-id="eb118-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="eb118-133">この型は、Q # 関数または操作が情報を返さないことを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="eb118-134">`true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`、および `Zero` の定数はすべて、Q # の予約済みの記号です。</span><span class="sxs-lookup"><span data-stu-id="eb118-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="eb118-135">配列型</span><span class="sxs-lookup"><span data-stu-id="eb118-135">Array Types</span></span>

<span data-ttu-id="eb118-136">有効な Q # 型 `'T`が指定されている場合は、`'T`型の値の配列を表す型があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="eb118-137">この配列型は `'T[]`として表されます。たとえば、`Qubit[]` や `Int[][]`のようになります。</span><span class="sxs-lookup"><span data-stu-id="eb118-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="eb118-138">たとえば、整数のコレクションは `Int[]`を示し、`(Bool, Pauli)` 値の配列の配列は `(Bool, Pauli)[][]`を示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="eb118-139">2番目の例では、これは、四角形の2次元配列ではなく、配列のジャグ配列を表すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eb118-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="eb118-140">Q # では、四角形多次元配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eb118-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="eb118-141">配列の値は、`[PauliI, PauliX, PauliY, PauliZ]`のように、配列の要素を角かっこで囲むことによって、Q # のソースコードで書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="eb118-142">配列リテラルの型は、配列内のすべての項目の共通基本型によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="eb118-143">配列の要素は、配列の作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="eb118-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="eb118-144">更新と再割り当てのステートメント、またはコピーと更新の式を使用して、変更された配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="eb118-145">または、`new` キーワードを使用して、配列のサイズから配列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb118-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="eb118-146">どちらの場合も、配列が構築されると、コア関数 `Length` を使用して、`Int`として要素の数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="eb118-147">配列は、角かっこを使用して下付き文字にすることができます。また、添字 `Int` または型 `Range`のいずれかを使用して、配列の要素のサブセットを含む単一の要素または新しい配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb118-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="eb118-148">配列の添字は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="eb118-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="eb118-149">タプル型</span><span class="sxs-lookup"><span data-stu-id="eb118-149">Tuple Types</span></span>

<span data-ttu-id="eb118-150">`T0`、`T1`、...、`Tn`という0個以上の型が指定されている場合は、新しい*タプル型*を `(T0, T1, ..., Tn)`として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="eb118-151">新しいタプル型を構築するために使用される型は、`(Int, (Qubit, Qubit))`のように、それ自体をタプルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="eb118-152">ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。</span><span class="sxs-lookup"><span data-stu-id="eb118-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="eb118-153">新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。</span><span class="sxs-lookup"><span data-stu-id="eb118-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="eb118-154">たとえば、`(3, false)` は、`(Int, Bool)`タプル型のタプルです。</span><span class="sxs-lookup"><span data-stu-id="eb118-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="eb118-155">組、配列の組、サブタプルの組などの配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="eb118-156">Q # 0.3 の場合、`Unit` は空のタプルの*型*の名前です。空のタプル*値*には `()` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="eb118-157">タプルインスタンスは変更できません。</span><span class="sxs-lookup"><span data-stu-id="eb118-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="eb118-158">Q # には、作成されたタプルの内容を変更する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="eb118-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="eb118-159">タプルは、1つの値に値をまとめて収集し、それらを簡単に渡すことができるようにするために、Q # 全体で使用される強力な概念です。</span><span class="sxs-lookup"><span data-stu-id="eb118-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="eb118-160">特に、タプル表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、ただ1つの出力を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="eb118-161">シングルトンタプルの等価性</span><span class="sxs-lookup"><span data-stu-id="eb118-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="eb118-162">`(5)` や `([1,2,3])`など、シングルトン (単一要素) の組を `('T1)`作成することができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="eb118-163">ただし、Q # は、シングルトンタプルを、囲まれた型の値と完全に等価なものとして扱います。</span><span class="sxs-lookup"><span data-stu-id="eb118-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="eb118-164">つまり、`5` と `(5)`、`5` と `(((5)))`の間、または `(5, (6))` と `(5, 6)`の間に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="eb118-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="eb118-165">この等価性は、代入式や式など、すべての目的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="eb118-166">これは、`5+3`書き込み `(5)+3` として記述するのと同じです。両方の式が `8`として評価されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="eb118-167">特に、これは、入力タプルまたは出力タプル型が1つのフィールドを持つ演算または関数は、1つの引数を受け取るか、単一の値を返すと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="eb118-168">このプロパティは、_シングルトンタプルの等価性_と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="eb118-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="eb118-169">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="eb118-169">User-Defined Types</span></span>

<span data-ttu-id="eb118-170">Q # ファイルでは、任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="eb118-171">`T`タプル型の場合、`newtype` ステートメントを使用して `T` のサブタイプである新しいユーザー定義型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="eb118-172">たとえば、@"microsoft.quantum.math" 名前空間では、複素数はユーザー定義型として定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="eb118-173">このステートメントは、`Double`型の2つの匿名項目を持つ新しい型を作成します。</span><span class="sxs-lookup"><span data-stu-id="eb118-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="eb118-174">ユーザー定義型では、匿名項目以外に、Q # バージョン0.7 以降の名前付き項目もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eb118-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="eb118-175">たとえば、複素数の実数部を表す double 型の `Re` to 項目には、虚数部の `Im` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="eb118-176">ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます</span><span class="sxs-lookup"><span data-stu-id="eb118-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="eb118-177">さらに、内部項目にもという名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="eb118-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="eb118-178">次の例のように定義されている型 `Nested` には、基になる型 `(Double, (Int, String))`があります。この場合、型 `Int` の項目のみが指定され、その他のすべての項目は匿名になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="eb118-179">名前付き項目には、アクセス演算子 `::`から直接アクセスできるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="eb118-180">一方、匿名の項目にアクセスするには、後置演算子 `!`を使用して、ラップされた値を最初に抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="eb118-181">"ラップ解除" 演算子 (`!`) を使用すると、ユーザー定義型に含まれる値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="eb118-182">このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。</span><span class="sxs-lookup"><span data-stu-id="eb118-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="eb118-183">ラップ解除演算子は、ラップのレイヤーを1つだけラップ解除します。</span><span class="sxs-lookup"><span data-stu-id="eb118-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="eb118-184">複数のラップ解除演算子は、乗算された値にアクセスするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="eb118-185">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-185">For instance:</span></span>

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

<span data-ttu-id="eb118-186">詳細については、「[式のラップ](xref:microsoft.quantum.language.expressions#unwrap-expressions)解除」と「[演算子の優先順位](xref:microsoft.quantum.language.expressions#operator-precedence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb118-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="eb118-187">ユーザー定義型の値は、対応する型コンストラクターを呼び出すことによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="eb118-188">または、[コピーと更新の式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb118-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="eb118-189">配列の場合と同様に、このような式は、指定された名前付き項目を除き、元の式のすべての項目の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eb118-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="eb118-190">これらの値は、式の右辺に定義されている値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="eb118-191">配列項目で使用できるその他の言語構成要素は[、たとえば、](xref:microsoft.quantum.language.statements#update-and-reassign-statement)ユーザー定義型の名前付き項目にも存在します。</span><span class="sxs-lookup"><span data-stu-id="eb118-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="eb118-192">ユーザー定義型は、他の型を使用できる場所であればどこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="eb118-193">特に、ユーザー定義型の配列を定義し、タプル型の要素としてユーザー定義型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="eb118-194">再帰型構造を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="eb118-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="eb118-195">つまり、ユーザー定義型を定義する型を、ユーザー定義型の要素を含むタプル型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb118-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="eb118-196">一般に、ユーザー定義型は相互に循環依存関係がない場合があるため、次の型定義のセットは無効になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="eb118-197">複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義する大きな利点の1つは、特定の値の意図を文書化できることです。</span><span class="sxs-lookup"><span data-stu-id="eb118-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="eb118-198">`Complex`の例に戻ると、1つのユーザー定義型として2D 極座標座標を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb118-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="eb118-199">`Complex` と `Polar` の両方に基になる型 `(Double, Double)`があるにもかかわらず、2つの型は両方とも Q # で完全には互換性がないため、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="eb118-200">このようにして、ユーザー定義型にはレコードと同様F#のロールがあります (例:)。</span><span class="sxs-lookup"><span data-stu-id="eb118-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="eb118-201">操作と関数の型</span><span class="sxs-lookup"><span data-stu-id="eb118-201">Operation and Function Types</span></span>

<span data-ttu-id="eb118-202">Q #_操作_は、クォンタムサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="eb118-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="eb118-203">つまり、量子操作を含む呼び出し可能なルーチンです。</span><span class="sxs-lookup"><span data-stu-id="eb118-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="eb118-204">Q #_関数_は、クォンタムアルゴリズム内で使用される古典的なサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="eb118-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="eb118-205">これには、従来のコードが含まれていても、クォンタム操作は含まれません。</span><span class="sxs-lookup"><span data-stu-id="eb118-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="eb118-206">具体的には、関数は、qubits の割り当てや借用を行うことも、操作を呼び出すこともできません。</span><span class="sxs-lookup"><span data-stu-id="eb118-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="eb118-207">ただし、処理のために操作または qubits を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="eb118-208">したがって、関数は、同じ引数でそれらを呼び出すと、常に同じ結果が生成されるという意味で完全に決定的です。</span><span class="sxs-lookup"><span data-stu-id="eb118-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="eb118-209">操作と関数は、共に_呼び出しを_実行できると呼びます。</span><span class="sxs-lookup"><span data-stu-id="eb118-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="eb118-210">これらの[例](#examples)を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="eb118-211">すべての Q # 呼び出しが、1つの値を入力として受け取り、1つの値を出力として返すと見なされます。</span><span class="sxs-lookup"><span data-stu-id="eb118-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="eb118-212">入力値と出力値は、どちらもタプルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="eb118-213">結果が返されない呼び出し可能性があり `Unit`。</span><span class="sxs-lookup"><span data-stu-id="eb118-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="eb118-214">入力がない callables は、空のタプルを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eb118-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="eb118-215">任意の呼び出し可能な基本型は `('Tinput => 'Tresult)` または `('Tinput -> 'Tresult)`として記述され、`'Tinput` と `'Tresult` の両方が型になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="eb118-216">操作には、`=>`を使用した最初の形式が使用されます。関数の2番目の形式 (`->`)。</span><span class="sxs-lookup"><span data-stu-id="eb118-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="eb118-217">たとえば、`((Qubit, Pauli) => Result)` は、単一の 1 qubit 測定操作のシグネチャを表します。</span><span class="sxs-lookup"><span data-stu-id="eb118-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="eb118-218">関数型は、シグネチャによって完全に指定されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="eb118-219">たとえば、角度のサインを計算する関数の型は `(Double -> Double)`になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="eb118-220">操作 (関数ではありません) には、操作の種類の一部として表現される特定の追加_特性_があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="eb118-221">このような特性には、操作がサポートする機能に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb118-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="eb118-222">機能は、基本操作の特殊化を生成するメタ操作です。下記の「ファンク[ター」を参照し](#functors)てください。</span><span class="sxs-lookup"><span data-stu-id="eb118-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="eb118-223">操作の種類は、入力の種類、出力の種類、およびその特性によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="eb118-224">操作の種類で `Controlled` または `Adjoint` ファンクタのサポートを必要とするために、対応する特性を示す注釈を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="eb118-225">たとえば、注釈 `is Ctl` は、操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="eb118-226">その型の操作で `Adjoint` と `Controlled` の両方のファンがサポートされるようにするには、これを `(Qubit => Unit is Adj + Ctl)`として表現します。</span><span class="sxs-lookup"><span data-stu-id="eb118-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="eb118-227">使用される操作特性 `Adj` および `Ctl` 厳密には、2つの定義済みラベルセットです。各ラベルは、特定のファンクタのサポートなど、特定の操作特性を示します。</span><span class="sxs-lookup"><span data-stu-id="eb118-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="eb118-228">したがって、これら2つのセットの和集合を示すために `+` が使用され、`*` が両方のセットに共通するラベルであるかどうかを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="eb118-229">たとえば、P# li `X` 操作には `(Qubit => Unit is Adj + Ctl)`型があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="eb118-230">すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。</span><span class="sxs-lookup"><span data-stu-id="eb118-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="eb118-231">型パラメーターの関数と操作</span><span class="sxs-lookup"><span data-stu-id="eb118-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="eb118-232">呼び出し可能な型には、型パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="eb118-233">型パラメーターは、1つの引用符で始まる記号で示されます。たとえば、`'A` は有効な型パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="eb118-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="eb118-234">1つのシグネチャで、型パラメーターが複数回出現する場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="eb118-235">たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャ `(('A[], 'A->'A) -> 'A[])`になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="eb118-236">同様に、2つの操作の構成を返す関数には `((('A=>'B), ('B=>'C)) -> ('A=>'C))`シグネチャがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="eb118-237">型パラメーターの呼び出し可能な呼び出しを呼び出すときは、同じ型パラメーターを持つすべての引数が同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="eb118-238">Q # には、型パラメーターに置き換えられる可能性のある型を制限する機構が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="eb118-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="eb118-239">型の互換性</span><span class="sxs-lookup"><span data-stu-id="eb118-239">Type Compatibility</span></span>

<span data-ttu-id="eb118-240">追加のファンクターがサポートされている操作は、より小さい値を持つ操作のすべての場所で使用できますが、同じシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb118-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="eb118-241">たとえば、型 `(Qubit => Unit is Adj)` の操作は、型 `(Qubit => Unit)` の操作が必要な場所であればどこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="eb118-242">Q # は、呼び出し可能な戻り値の型に関して共変です。同じ入力型の呼び出し可能なと互換性がある `'A` 型を返す呼び出し可能な型と、と互換性がある `'A` の結果型です。</span><span class="sxs-lookup"><span data-stu-id="eb118-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="eb118-243">Q # は、入力の型に関して反変です。入力と同じ結果型の呼び出し可能な型と、`'A`と互換性のある入力型との互換性があるという点で、型 `'A` を受け取る呼び出し可能な。</span><span class="sxs-lookup"><span data-stu-id="eb118-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="eb118-244">つまり、次の定義を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb118-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="eb118-245">次のことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="eb118-245">the following are true:</span></span>

- <span data-ttu-id="eb118-246">関数 `ConjugateInvertWith` は `Invert` または `ApplyUnitary`のいずれかの `inner` 引数を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="eb118-247">関数 `ConjugateUnitaryWith` は `ApplyUnitary`の `inner` 引数を使用して呼び出すことができますが、`Invert`は使用できません。</span><span class="sxs-lookup"><span data-stu-id="eb118-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="eb118-248">`ConjugateInvertWith`から `(Qubit[] => Unit is Adj + Ctl)` 型の値が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb118-249">Q # 0.3 では、ユーザー定義型の動作に大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="eb118-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="eb118-250">ユーザー定義型は、サブタイプとしてではなく、基になる型のラップされたバージョンとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="eb118-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="eb118-251">これは、基になる型の値が必要な場合に、ユーザー定義型の値を使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="eb118-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="eb118-252">ファンクター</span><span class="sxs-lookup"><span data-stu-id="eb118-252">Functors</span></span>

<span data-ttu-id="eb118-253">Q # のファンクタは、別の操作から新しい操作を定義するファクトリです。</span><span class="sxs-lookup"><span data-stu-id="eb118-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="eb118-254">新しい操作の実装を定義するときに、基本操作の実装にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eb118-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="eb118-255">したがって、関数は、従来の上位レベルの関数よりも複雑な関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="eb118-256">この型は、Q # 型システムには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="eb118-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="eb118-257">そのため、変数にバインドしたり、引数として渡したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb118-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="eb118-258">ファンクタは、操作に適用して新しい操作を返すことによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="eb118-259">たとえば、`Adjoint` のファンクタを `Y` 操作に適用した結果として得られる操作は、`Adjoint Y`として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="eb118-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="eb118-260">その後、他の操作と同様に、新しい操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="eb118-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="eb118-261">このため、`Adjoint Y(q1)` は、Adjoint ファンクタを `Y` 操作に適用して新しい操作を生成し、その新しい操作を `q1`に適用します。</span><span class="sxs-lookup"><span data-stu-id="eb118-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="eb118-262">同様に、`Controlled X(controls, target)` は制御されたファンを `X` 操作に適用して新しい操作を生成し、その新しい操作を `controls` および `target`に適用します。</span><span class="sxs-lookup"><span data-stu-id="eb118-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="eb118-263">Q # の2つの標準のファンクターは `Adjoint` と `Controlled`です。</span><span class="sxs-lookup"><span data-stu-id="eb118-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="eb118-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="eb118-264">Adjoint</span></span>

<span data-ttu-id="eb118-265">クォンタムコンピューティングでは、操作の adjoint は、操作の複雑な共役転置です。</span><span class="sxs-lookup"><span data-stu-id="eb118-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="eb118-266">ユニタリ演算子を実装する操作の場合、adjoint は演算の逆になります。</span><span class="sxs-lookup"><span data-stu-id="eb118-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="eb118-267">Qubits のセットに対して他の一連の処理を呼び出すだけの単純な操作の場合、同じ qubits にサブ操作の adjoint を逆順で適用することによって、adjoint を計算できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="eb118-268">操作式を指定した場合は、`Adjoint` ファンクタを使用して新しい演算式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="eb118-269">たとえば、`Adjoint QFT` は、`QFT` 操作の adjoint を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb118-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="eb118-270">新しい操作のシグネチャと型は、基本操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="eb118-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="eb118-271">特に、新しい操作では `Adjoint`が許可され、基本操作が行われた場合にのみ `Controlled` が許可されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="eb118-272">Adjoint ファンクタは、独自の逆になります。つまり、`Adjoint Adjoint Op` は常に `Op`と同じです。</span><span class="sxs-lookup"><span data-stu-id="eb118-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="eb118-273">た</span><span class="sxs-lookup"><span data-stu-id="eb118-273">Controlled</span></span>

<span data-ttu-id="eb118-274">操作の制御されたバージョンは、すべてのコントロール qubits が指定された状態にある場合にのみ、基本操作を効果的に適用する新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="eb118-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="eb118-275">コントロール qubits が法則内にある場合、基本操作は一貫の適切な部分に適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="eb118-276">したがって、制御された操作は、多くの場合、entangを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="eb118-277">Q # では、制御されたバージョンは常に制御 qubits の配列を取得します。また、指定した状態は、常に計算 (`PauliZ`) `One` 状態、$ \ket{1}$ に含まれるすべてのコントロール qubits に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="eb118-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="eb118-278">その他の状態に基づいて制御するには、制御された操作の前に適切なユニタリ操作を制御 qubits に適用し、次に、制御された操作の後に逆を適用します。</span><span class="sxs-lookup"><span data-stu-id="eb118-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="eb118-279">たとえば、制御された操作の前後のコントロール qubit に `X` 操作を適用すると、その qubit の `Zero` 状態 ($ \ket{0}$) に対して操作が制御されます。の前と後に `H` 操作を適用すると、`PauliX` の `One` の状態を制御します。これは、{0}{1}状態ではなく、P# li X、$ \ket{-} \mathrel{: =} (\ket{2}-\ket `PauliZ`)/\ sqrt `One` $ の-1 eigenvalue です。</span><span class="sxs-lookup"><span data-stu-id="eb118-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="eb118-280">操作式を指定した場合は、`Controlled` ファンクタを使用して新しい演算式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="eb118-281">新しい操作の署名は、元の操作の署名に基づいています。</span><span class="sxs-lookup"><span data-stu-id="eb118-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="eb118-282">結果の型は同じですが、入力の型は2つのタプルで、最初の要素としてコントロール qubit を保持し、2番目の要素として元の操作の引数を保持します。</span><span class="sxs-lookup"><span data-stu-id="eb118-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="eb118-283">新しい操作では `Controlled`がサポートされ、元の操作が行われた場合にのみ、`Adjoint` がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eb118-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="eb118-284">元の操作で1つの引数のみを取得した場合は、シングルトン組の等価性がここで再生されます。</span><span class="sxs-lookup"><span data-stu-id="eb118-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="eb118-285">たとえば、`Controlled X` は、`X` 操作の制御されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="eb118-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="eb118-286">`X` に型 `(Qubit => Unit is Adj + Ctl)`があるため、`Controlled X` の型は `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`です。シングルトンタプルの等価性のため、これは `((Qubit[], Qubit) => Unit is Adj + Ctl)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="eb118-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="eb118-287">基本操作に複数の引数を指定する場合は、操作の制御されたバージョンの対応する引数をかっこで囲み、それらをタプルに変換してください。</span><span class="sxs-lookup"><span data-stu-id="eb118-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="eb118-288">たとえば、`Controlled Rz` は、`Rz` 操作の制御されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="eb118-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="eb118-289">`Rz` に型 `((Double, Qubit) => Unit is Adj + Ctl)`があるため、`Controlled Rz` には `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`型があります。</span><span class="sxs-lookup"><span data-stu-id="eb118-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="eb118-290">したがって、`Controlled Rz(controls, (0.1, target))` は `Controlled Rz` の有効な呼び出しです (`0.1, target`を囲むかっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="eb118-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="eb118-291">もう1つの例として、`CNOT(control, target)` を `Controlled X([control], target)`として実装できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="eb118-292">ターゲットを2つの制御 qubits (CCNOT) で制御する必要がある場合は、`Controlled X([control1, control2], target)` ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="eb118-293">例</span><span class="sxs-lookup"><span data-stu-id="eb118-293">Examples</span></span>

<span data-ttu-id="eb118-294">この Q # 操作の例は、[測定](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)サンプルから取得したものです。</span><span class="sxs-lookup"><span data-stu-id="eb118-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="eb118-295">操作内では、qubits を割り当てて、`H` や `X`などの qubits に対してクォンタム操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb118-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="eb118-296">この関数の例は、 [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)サンプルを基にしています。</span><span class="sxs-lookup"><span data-stu-id="eb118-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="eb118-297">純粋にクラシックコードを含みます。</span><span class="sxs-lookup"><span data-stu-id="eb118-297">It contains purely classical code.</span></span> <span data-ttu-id="eb118-298">上記の例とは異なり、qubits は割り当てられず、クォンタム操作は使用されません。</span><span class="sxs-lookup"><span data-stu-id="eb118-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="eb118-299">[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)サンプルの例のように、処理のために関数に qubits を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="eb118-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="eb118-300">Qubits は関数に渡され、処理に使用されます。ただし、どのポイントも qubits の状態自体が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="eb118-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
