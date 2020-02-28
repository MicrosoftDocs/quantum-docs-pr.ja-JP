---
title: 'Q # の式'
description: 'Q # の式として、定数、変数、演算子、操作、関数を指定、参照、および結合する方法について説明します。'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907411"
---
# <a name="expressions"></a><span data-ttu-id="b48fa-103">式</span><span class="sxs-lookup"><span data-stu-id="b48fa-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="b48fa-104">グループ化</span><span class="sxs-lookup"><span data-stu-id="b48fa-104">Grouping</span></span>

<span data-ttu-id="b48fa-105">任意の式を指定すると、かっこで囲まれた同じ式が同じ型の式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="b48fa-106">たとえば、`(7)` は `Int` 式で、`([1,2,3])` は `Int`s の型配列の式であり、`((1,2))` は型 `(Int, Int)`の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="b48fa-107">[型モデル](xref:microsoft.quantum.language.type-model#tuple-types)で記述されている単純値と単一要素の組の等価性により、`(6)` とグループとしてのあいまいさが解消され、単一要素のタプルとして `(6)` ます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="b48fa-108">記号</span><span class="sxs-lookup"><span data-stu-id="b48fa-108">Symbols</span></span>

<span data-ttu-id="b48fa-109">`'T` 型の値にバインドまたは割り当てられたシンボルの名前は `'T`型の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="b48fa-110">たとえば、シンボル `count` が整数値 `5`にバインドされている場合、`count` は整数式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="b48fa-111">数値式</span><span class="sxs-lookup"><span data-stu-id="b48fa-111">Numeric Expressions</span></span>

<span data-ttu-id="b48fa-112">数値式は `Int`、`BigInt`、または `Double`型の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="b48fa-113">つまり、整数または浮動小数点数のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="b48fa-114">Q # のリテラル `Int` は、のC#整数リテラルと同じですが、末尾の "l" または "l" が不要 (または許可) である点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="b48fa-115">16進数とバイナリ整数は、それぞれ "0x" プレフィックスと "0b" プレフィックスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="b48fa-116">Q # のリテラル `BigInt` は、.NET では、末尾に "l" または "L" が付いた大きな整数の文字列と同じです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="b48fa-117">16進数の大きな整数は、プレフィックス "0x" でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="b48fa-118">したがって、`BigInt` リテラルのすべての有効な使用法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="b48fa-119">Q # のリテラル `Double` は、の2つのC#リテラルと同じですが、末尾の "d" または "d" が不要 (または許可) である点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="b48fa-120">任意の要素型の配列式が指定されている場合、`Length` の組み込み関数を使用して `Int` 式を作成できます。また、かっこ、`(`、および `)`で囲まれた配列式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="b48fa-121">たとえば、`a` が配列にバインドされている場合、`Length(a)` は整数式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="b48fa-122">`b` が整数の配列の配列である場合、`Int[][]`、`Length(b)` は `b`内のサブ配列の数、`Length(b[1])` は `b`の2番目のサブ配列の整数の数です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="b48fa-123">同じ型の2つの数値式を指定した場合、2項演算子 `+`、`-`、`*`、および `/` を使用して、新しい数値式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="b48fa-124">新しい式の型は、構成式の型と同じになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="b48fa-125">2つの整数式を指定すると、二項演算子 `^` (累乗) を使用して新しい整数式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="b48fa-126">同様に、2つの double 式で `^` を使用して、新しい double 式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="b48fa-127">最後に、`^` は、左側の大きな整数と右にある整数を使用して、新しい大きな整数式を形成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="b48fa-128">この場合、2番目のパラメーターは32ビットにする必要があります。それ以外の場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="b48fa-129">2つの整数または整数式が指定されている場合は、`%` (剰余)、`&&&` (ビット演算 AND)、`|||` (ビットごとの OR) 演算子、または `^^^` (ビットごとの XOR) 演算子を使用して、新しい整数または大きな整数式が形成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="b48fa-130">左側に整数または整数式が指定されていて、右側に整数式が指定されている場合は、`<<<` (算術左シフト) 演算子または `>>>` (算術右シフト) 演算子を使用して、左側の式と同じ型の新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="b48fa-131">シフト演算の2番目のパラメーター (シフト量) は、0以上である必要があります。負のシフト量の動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="b48fa-132">また、いずれかのシフト操作のシフト量は、32ビットにも適合する必要があります。それ以外の場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="b48fa-133">シフトする数値が整数である場合、シフト数は `mod 64`に解釈されます。つまり、シフト1と65のシフトは同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="b48fa-134">整数値と大きな整数値の両方に対して、シフトは算術演算です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="b48fa-135">負の値を左または右にシフトすると、負の数値になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="b48fa-136">つまり、1つのステップを左または右にシフトすることは、それぞれ2で乗算または除算するのとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="b48fa-137">整数の除算と整数の剰余は、負の数値のC#場合と同じ動作に従います。</span><span class="sxs-lookup"><span data-stu-id="b48fa-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="b48fa-138">つまり、`a % b` は常に `a`と同じ符号を持ち、`b * (a / b) + a % b` は常に `a`と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="b48fa-139">例 :</span><span class="sxs-lookup"><span data-stu-id="b48fa-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="b48fa-140">5</span><span class="sxs-lookup"><span data-stu-id="b48fa-140">5</span></span> | <span data-ttu-id="b48fa-141">2</span><span class="sxs-lookup"><span data-stu-id="b48fa-141">2</span></span> | <span data-ttu-id="b48fa-142">2</span><span class="sxs-lookup"><span data-stu-id="b48fa-142">2</span></span> | <span data-ttu-id="b48fa-143">1</span><span class="sxs-lookup"><span data-stu-id="b48fa-143">1</span></span>
 <span data-ttu-id="b48fa-144">5</span><span class="sxs-lookup"><span data-stu-id="b48fa-144">5</span></span> | <span data-ttu-id="b48fa-145">-2</span><span class="sxs-lookup"><span data-stu-id="b48fa-145">-2</span></span> | <span data-ttu-id="b48fa-146">-2</span><span class="sxs-lookup"><span data-stu-id="b48fa-146">-2</span></span> | <span data-ttu-id="b48fa-147">1</span><span class="sxs-lookup"><span data-stu-id="b48fa-147">1</span></span>
 <span data-ttu-id="b48fa-148">-5</span><span class="sxs-lookup"><span data-stu-id="b48fa-148">-5</span></span> | <span data-ttu-id="b48fa-149">2</span><span class="sxs-lookup"><span data-stu-id="b48fa-149">2</span></span> | <span data-ttu-id="b48fa-150">-2</span><span class="sxs-lookup"><span data-stu-id="b48fa-150">-2</span></span> | <span data-ttu-id="b48fa-151">-1</span><span class="sxs-lookup"><span data-stu-id="b48fa-151">-1</span></span>
 <span data-ttu-id="b48fa-152">-5</span><span class="sxs-lookup"><span data-stu-id="b48fa-152">-5</span></span> | <span data-ttu-id="b48fa-153">-2</span><span class="sxs-lookup"><span data-stu-id="b48fa-153">-2</span></span> | <span data-ttu-id="b48fa-154">2</span><span class="sxs-lookup"><span data-stu-id="b48fa-154">2</span></span> | <span data-ttu-id="b48fa-155">-1</span><span class="sxs-lookup"><span data-stu-id="b48fa-155">-1</span></span>

<span data-ttu-id="b48fa-156">大規模な整数除算と剰余は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="b48fa-157">任意の数値式を指定した場合は、`-` 単項演算子を使用して新しい式を形成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="b48fa-158">新しい式は、構成式と同じ型になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="b48fa-159">整数または整数式が指定されている場合、同じ型の新しい式は、`~~~` (ビットごとの補数) 単項演算子を使用して形成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="b48fa-160">Boolean 式</span><span class="sxs-lookup"><span data-stu-id="b48fa-160">Boolean Expressions</span></span>

<span data-ttu-id="b48fa-161">2つの `Bool` リテラル値は `true` と `false`です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="b48fa-162">同じプリミティブ型の2つの式を指定すると、`==` および `!=` 二項演算子を使用して `Bool` 式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="b48fa-163">2つの式が等しい場合、式は true になり、そうでない場合は false になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="b48fa-164">ユーザー定義型の値を比較することはできません。ラップ解除された値だけを比較できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="b48fa-165">たとえば、"ラップ解除" 演算子 ([ [Q # type model] ページ](xref:microsoft.quantum.language.type-model#user-defined-types)で説明) `!` を使用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="b48fa-166">`Qubit` 値の等価比較は id の等価性を比較します。つまり、2つの式が同じ qubit を識別するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="b48fa-167">2つの qubits の状態は、この比較によって比較、アクセス、測定、または変更されません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="b48fa-168">丸め効果により、`Double` 値の等価比較が誤解を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="b48fa-169">たとえば、`49.0 * (1.0/49.0) != 1.0`します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="b48fa-170">2つの数値式を指定した場合、2項演算子 `>`、`<`、`>=`、および `<=` を使用して、新しいブール式を作成できます。この式は、最初の式の値が、2番目の式の値よりも大きい、より小さい、または等しいか、または等しい場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="b48fa-171">2つのブール式を指定すると、2つの式の両方 (resp または両方) が true の場合に true になる新しいブール式を作成するために、`and` および `or` のバイナリ演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="b48fa-172">ブール式が指定されている場合、`not` 単項演算子を使用して新しいブール式を作成できます。これは、構成式が false の場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="b48fa-173">文字列式</span><span class="sxs-lookup"><span data-stu-id="b48fa-173">String Expressions</span></span>

<span data-ttu-id="b48fa-174">Q # では、`fail` ステートメントと `Log` 標準関数で文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="b48fa-175">Q # の文字列は、リテラルまたは挿入文字列です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="b48fa-176">文字列リテラルは、ほとんどの言語の単純な文字列リテラルに似ています。これは、二重引用符で囲まれた一連の Unicode 文字 (`"`) です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="b48fa-177">文字列の内部では、バックスラッシュ文字 `\` を使用して二重引用符をエスケープし、改行を `\n`として挿入したり、`\r`としてキャリッジリターンを `\t`として挿入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="b48fa-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="b48fa-179">文字列補間の Q # 構文は、 C# 7.0 構文のサブセットです。Q # では、逐語的 (複数行) の補間文字列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="b48fa-180">構文についてはC# 、「[*補間文字列*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48fa-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="b48fa-181">挿入文字列内の式は、構文ではなくC# Q # 構文に従います。</span><span class="sxs-lookup"><span data-stu-id="b48fa-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="b48fa-182">有効な Q # 式は、挿入文字列に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="b48fa-183">Qubit 式</span><span class="sxs-lookup"><span data-stu-id="b48fa-183">Qubit Expressions</span></span>

<span data-ttu-id="b48fa-184">唯一の `Qubit` 式は、`Qubit` 配列の `Qubit` 値または配列要素にバインドされるシンボルです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="b48fa-185">`Qubit` リテラルがありません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="b48fa-186">P# li 式</span><span class="sxs-lookup"><span data-stu-id="b48fa-186">Pauli Expressions</span></span>

<span data-ttu-id="b48fa-187">4つの `Pauli` 値、`PauliI`、`PauliX`、`PauliY`、および `PauliZ`は、すべて有効な `Pauli` 式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="b48fa-188">それ以外の `Pauli` 式は、`Pauli` 配列の `Pauli` 値または配列要素にバインドされているシンボルのみです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="b48fa-189">結果式</span><span class="sxs-lookup"><span data-stu-id="b48fa-189">Result Expressions</span></span>

<span data-ttu-id="b48fa-190">`One` と `Zero`の2つの `Result` 値は、有効な `Result` 式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="b48fa-191">それ以外の `Result` 式は、`Result` 配列の `Result` 値または配列要素にバインドされているシンボルのみです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="b48fa-192">特に、`One` が整数 `1`と同じではなく、それらの間に直接変換がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b48fa-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="b48fa-193">`Zero` と `0`にも同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="b48fa-194">範囲の式</span><span class="sxs-lookup"><span data-stu-id="b48fa-194">Range Expressions</span></span>

<span data-ttu-id="b48fa-195">`start`、`step`、および `stop`の3つの `Int` 式が指定されている場合、`start .. step .. stop` が渡されるまで、最初の要素が `start`、2番目の要素が `start+step`、3番目の要素が `start+step+step`などの範囲式です。`stop`</span><span class="sxs-lookup"><span data-stu-id="b48fa-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="b48fa-196">たとえば、`step` が正および `stop < start`の場合、範囲は空になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="b48fa-197">`start` と `stop` の差が `step`の整数倍数である場合、範囲の最後の要素が `stop` されます。つまり、範囲は両端を含みます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="b48fa-198">`start` と `stop`の2つの `Int` 式が指定されている場合、`start .. stop` は `start .. 1 .. stop`と等しい範囲式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="b48fa-199">`stop` が `start`より小さい場合でも、暗黙の `step` は + 1 であることに注意してください。このような場合、範囲は空になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="b48fa-200">範囲の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-200">Some example ranges are:</span></span>

- <span data-ttu-id="b48fa-201">`1..3` の範囲は1、2、3です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="b48fa-202">`2..2..5` は2、4の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="b48fa-203">`2..2..6` は2、4、6の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="b48fa-204">`6..-2..2` は6、4、2の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="b48fa-205">`2..1` が空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="b48fa-206">`2..6..7` の範囲は2です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="b48fa-207">`2..2..1` が空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="b48fa-208">`1..-1..2` が空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="b48fa-209">呼び出し可能式</span><span class="sxs-lookup"><span data-stu-id="b48fa-209">Callable Expressions</span></span>

<span data-ttu-id="b48fa-210">呼び出し可能なリテラルは、コンパイルスコープで定義されている操作または関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="b48fa-211">たとえば、`X` は標準ライブラリ `X` 操作を参照する操作リテラルであり、`Message` は標準ライブラリ `Message` 関数を参照する関数リテラルです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="b48fa-212">操作で `Adjoint` ファンクタがサポートされている場合、`Adjoint op` は演算式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="b48fa-213">同様に、操作で `Controlled` ファンクタがサポートされている場合、`Controlled op` は演算式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="b48fa-214">これらの式の型は、ファンクターで指定され[ます。](xref:microsoft.quantum.language.type-model#functors)</span><span class="sxs-lookup"><span data-stu-id="b48fa-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="b48fa-215">ファンクター (`Adjoint` および `Controlled`) は、ラップ解除演算子 `!` および `[]`での配列インデックス作成を除き、他のすべての演算子よりも密接にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="b48fa-216">このため、操作で使用されている機能がサポートされていれば、次のすべての処理が有効になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="b48fa-217">呼び出し可能なリテラルは、値として使用できます。たとえば、変数に代入する場合や、別の呼び出し可能に渡す場合です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="b48fa-218">この場合、呼び出し可能な型パラメーターがある場合は、呼び出し可能な値の一部として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="b48fa-219">呼び出し可能な値には、指定されていない型パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b48fa-220">たとえば、`Fun` がシグネチャ `'T1->Unit`の関数の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="b48fa-221">呼び出し可能呼び出し式</span><span class="sxs-lookup"><span data-stu-id="b48fa-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="b48fa-222">呼び出し可能なシグネチャの入力型の呼び出し可能な (操作または関数) 式と組式が指定されている場合、呼び出し式は、呼び出し可能な式にタプル式を追加することによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="b48fa-223">呼び出し式の型は、呼び出し可能なシグネチャの出力型です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="b48fa-224">たとえば、`Op` がシグネチャ `((Int, Qubit) => Double)`を持つ操作の場合、`Op(3, qubit1)` は `Double`型の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b48fa-225">同様に、`Sin` がシグネチャ `(Double -> Double)`を持つ関数の場合、`Sin(0.1)` は `Double`型の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b48fa-226">最後に、`Builder` がシグネチャ `(Int -> (Int -> Int))`の関数である場合、`Builder(3)` は Into から Int への関数になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="b48fa-227">呼び出し可能な値の式の結果を呼び出すには、呼び出し可能な式を囲むかっこのペアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="b48fa-228">したがって、前の段落から `Builder` を呼び出した結果を呼び出すために、正しい構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="b48fa-229">型パラメーター呼び出し可能呼び出しを呼び出すときに、実際の型パラメーターを山かっこ内に指定して、呼び出し可能な式の後に `>` `<` ことができます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="b48fa-230">これは通常、Q # コンパイラによって実際の型が推論されるため、不要です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="b48fa-231">型パラメーターの引数が指定されていない場合は、部分的なアプリケーション (下記参照) に必要です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="b48fa-232">また、異なるファンのサポートを持つ操作を呼び出し可能に渡す場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="b48fa-233">たとえば、`Func` に署名 `('T1, 'T2, 'T1) -> 'T2`がある場合、`Op1` と `Op2` に署名 `(Qubit[] => Unit is Adj)`があり、`Op3` に署名 `(Qubit[] => Unit)`があり、1番目の引数として `Func` を呼び出して、3番目の引数として `Op1` します。`Op2``Op3`</span><span class="sxs-lookup"><span data-stu-id="b48fa-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="b48fa-234">`Op3` と `Op1` の型が異なるため、型指定が必要です。そのため、コンパイラはこれを仕様なしにあいまいとして扱います。</span><span class="sxs-lookup"><span data-stu-id="b48fa-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="b48fa-235">部分アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b48fa-235">Partial Application</span></span>

<span data-ttu-id="b48fa-236">呼び出し可能な式が指定されている場合は、呼び出し可能な引数のサブセットを指定することによって、新しい呼び出し可能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="b48fa-237">これは、_部分的なアプリケーション_と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-237">This is called _partial application_.</span></span>

<span data-ttu-id="b48fa-238">Q # では、部分的に適用された呼び出し可能は、通常の呼び出し式を記述することによって表されますが、指定されていない引数にはアンダースコア (`_`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="b48fa-239">結果として得られる呼び出し元は、基本の呼び出し元と同じ結果型と、操作に対して同じ特殊化を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="b48fa-240">部分アプリケーションの入力型は、指定された引数が削除された元の型にすぎません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="b48fa-241">部分アプリケーションの作成時に、変更可能な変数が指定された引数として渡される場合は、変数の現在の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="b48fa-242">後で変数の値を変更しても、部分的なアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="b48fa-243">たとえば、`Op` の型が `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`の場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="b48fa-244">`Op(5,(_,_))` に `(((Qubit,Qubit), Double) => Unit is Adj)`型があるため、`Op(5,_)`があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="b48fa-245">`Op(_,(_,1.0))` に `((Int, (Qubit,Qubit)) => Unit is Adj)`型があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="b48fa-246">`Op(_,((q1,q2),_))` に `((Int,Double) => Unit is Adj)`型があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="b48fa-247">ここでは、シングルトンタプルの等価性が適用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b48fa-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="b48fa-248">部分的に適用される呼び出し可能な型パラメーターがコンパイラによって推論できない場合は、呼び出しサイトで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="b48fa-249">部分アプリケーションは、指定されていない型パラメーターを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b48fa-250">たとえば、`Op` の型が `(('T1, Qubit, 'T1) => Unit : Adjoint)`の場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="b48fa-251">再帰</span><span class="sxs-lookup"><span data-stu-id="b48fa-251">Recursion</span></span>

<span data-ttu-id="b48fa-252">Q # callables は、直接的または間接的に再帰的に許可されています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="b48fa-253">つまり、操作または関数はそれ自体を呼び出すことができます。または、呼び出し可能な操作を直接または間接的に呼び出す別の呼び出し元を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="b48fa-254">ただし、再帰の使用に関しては、次の2つの重要なコメントがあります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="b48fa-255">操作で再帰を使用すると、特定の最適化が妨げられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="b48fa-256">これは、アルゴリズムの実行時間に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="b48fa-257">実際のクォンタムデバイスで実行すると、スタック領域が制限される可能性があるため、詳細な再帰によって実行時エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="b48fa-258">特に、Q # コンパイラとランタイムは、末尾の再帰を識別して最適化しません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="b48fa-259">タプル式</span><span class="sxs-lookup"><span data-stu-id="b48fa-259">Tuple Expressions</span></span>

<span data-ttu-id="b48fa-260">組リテラルは、適切な型の要素式のシーケンスであり、コンマで区切られ、`(` と `)`で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="b48fa-261">たとえば、`(1, One)` は `(Int, Result)` 式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="b48fa-262">リテラル以外の唯一のタプル式は、タプル値にバインドされたシンボル、組配列の配列要素、およびタプルを返す呼び出し可能な呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="b48fa-263">ユーザー定義型の式</span><span class="sxs-lookup"><span data-stu-id="b48fa-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="b48fa-264">ユーザー定義型のリテラルは、型名の後に型の基本タプル型のタプルリテラルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="b48fa-265">たとえば、`IntPair` が `(Int, Int)`に基づくユーザー定義型である場合、`IntPair(2,3)` はその型の有効なリテラルになります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="b48fa-266">リテラル以外に、ユーザー定義型の唯一の式は、その型の値、その型の配列の配列要素、およびその型を返す呼び出し可能な呼び出しの値にバインドされている記号です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="b48fa-267">ラップ解除 (式の)</span><span class="sxs-lookup"><span data-stu-id="b48fa-267">Unwrap Expressions</span></span>

<span data-ttu-id="b48fa-268">Q # では、ラップ解除演算子は、末尾の感嘆符 `!`になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="b48fa-269">たとえば、`IntPair` が基になる型が `(Int, Int)`であるユーザー定義型で、`s` が値 `IntPair(2,3)`の変数である場合、`s!` が `(2,3)`されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="b48fa-270">他のユーザー定義型の観点から定義されたユーザー定義型の場合。</span><span class="sxs-lookup"><span data-stu-id="b48fa-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="b48fa-271">ラップ解除演算子は、繰り返すことができます。たとえば、`s!!` は `s`のダブルラップされていない値を示します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="b48fa-272">したがって `WrappedPair` が基になる型が `IntPair`であるユーザー定義型で、`t` が値 `WrappedPair(IntPair(1,2))`の変数である場合、`t!!` が `(1,2)`されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="b48fa-273">`!` 演算子は、配列のインデックス作成とスライスのために `[]` 以外の他のすべての演算子より優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="b48fa-274">`!` と `[]` bind 位置;つまり、`a[i]![3]` を `((a[i])!)[3]`として読み取る必要があります。 `a`の `i`' 番目の要素を取得してラップを解除し、ラップ解除された値の3番目の要素 (配列である必要があります) を取得します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="b48fa-275">`!` 演算子の優先順位には、明らかでない可能性がある1つの影響があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="b48fa-276">関数または操作が、ラップされていない値を返す場合は、ラップ解除ではなく、引数のタプルが呼び出しにバインドされるように、関数または操作の呼び出しをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="b48fa-277">例 :</span><span class="sxs-lookup"><span data-stu-id="b48fa-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="b48fa-278">配列式</span><span class="sxs-lookup"><span data-stu-id="b48fa-278">Array Expressions</span></span>

<span data-ttu-id="b48fa-279">配列リテラルは、`[` および `]`で囲まれた、コンマで区切られた1つ以上の要素式のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="b48fa-280">すべての要素は、同じ型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="b48fa-281">共通の要素型が演算型または関数型である場合、すべての要素の入力と出力の型が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="b48fa-282">配列の要素型は、すべての要素でサポートされているすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b48fa-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="b48fa-283">たとえば、`Op1`、`Op2`、および `Op3` はすべて `Qubit[] => Unit`ですが、`Op1` は `Adjoint`をサポートし、`Op2` は両方をサポートします。`Controlled``Op3`</span><span class="sxs-lookup"><span data-stu-id="b48fa-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b48fa-284">`[Op1, Op2]` は `(Qubit[] => Unit)` 操作の配列です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="b48fa-285">`[Op1, Op3]` は `(Qubit[] => Unit is Adj)` 操作の配列です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="b48fa-286">`[Op2, Op3]` は `(Qubit[] => Unit is Ctl)` 操作の配列です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="b48fa-287">空の配列リテラル `[]`は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="b48fa-288">代わりに `new ★[0]`を使用します。 `★` は適切な型のプレースホルダーとして使用されるため、では、必要な長さゼロの配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="b48fa-289">同じ型の2つの配列を指定した場合、2つの配列を連結した新しい配列を形成するために、バイナリ `+` 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="b48fa-290">たとえば、`[1,2,3] + [4,5,6]` は `[1,2,3,4,5,6]`です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="b48fa-291">配列の作成</span><span class="sxs-lookup"><span data-stu-id="b48fa-291">Array Creation</span></span>

<span data-ttu-id="b48fa-292">型と `Int` 式が指定されている場合、`new` 演算子を使用して、指定されたサイズの新しい配列を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="b48fa-293">たとえば、`new Int[i+1]` は `i+1` 要素を持つ新しい `Int` 配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="b48fa-294">新しい配列の要素は、型に依存する既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="b48fa-295">ほとんどの場合、これはゼロのバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="b48fa-296">エンティティへの参照である qubits と callables 指定できる場合、適切な既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="b48fa-297">したがって、これらの型では、既定値は無効な参照で、ランタイムエラーを発生させずに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b48fa-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="b48fa-298">これは、や Java などの言語での null C#参照に似ています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="b48fa-299">Qubits または callables 含む配列は、要素が安全に使用される前に、既定値以外の値で適切に初期化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="b48fa-300">適切な初期化ルーチンについては、<xref:microsoft.quantum.arrays>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48fa-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b48fa-301">各型の既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b48fa-301">The default values for each type are:</span></span>

<span data-ttu-id="b48fa-302">種類</span><span class="sxs-lookup"><span data-stu-id="b48fa-302">Type</span></span> | <span data-ttu-id="b48fa-303">既定値</span><span class="sxs-lookup"><span data-stu-id="b48fa-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="b48fa-304">_無効な qubit_</span><span class="sxs-lookup"><span data-stu-id="b48fa-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="b48fa-305">空の範囲、`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="b48fa-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="b48fa-306">_無効な呼び出し可能_</span><span class="sxs-lookup"><span data-stu-id="b48fa-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="b48fa-307">タプル型は要素ごとに初期化されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="b48fa-308">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="b48fa-308">Jagged Arrays</span></span>

<span data-ttu-id="b48fa-309">ジャグ配列は、"配列の配列" と呼ばれることもあり、要素が配列である配列です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="b48fa-310">ジャグ配列の要素のサイズは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="b48fa-311">次の例は、乗算テーブルを表すジャグ配列を宣言および初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="b48fa-312">配列スライス</span><span class="sxs-lookup"><span data-stu-id="b48fa-312">Array Slices</span></span>

<span data-ttu-id="b48fa-313">配列式と `Range` 式が指定されている場合は、`[` と `]` の配列スライス演算子を使用して新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="b48fa-314">新しい式は配列と同じ型になり、`Range`の要素によってインデックス付けされた配列項目が、`Range`で定義されている順序で格納されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="b48fa-315">たとえば、`a` が `Double`s の配列にバインドされている場合、`a[3..-1..0]` は、`a` の最初の4つの要素を含む `Double[]` 式です。ただし、`a`に表示される順序は逆になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="b48fa-316">`Range` が空の場合、結果として得られる配列スライスは長さ0になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="b48fa-317">配列式が単純識別子でない場合は、スライスするためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="b48fa-318">たとえば、`a` と `b` が両方とも `Int`の配列である場合、連結のスライスは次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="b48fa-319">Q # のすべての配列は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b48fa-320">つまり、配列 `a` の最初の要素は常に `a[0]`ます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="b48fa-321">0\.8 リリース以降では、範囲スライスのコンテキスト式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="b48fa-322">特に、範囲の開始値と終了値は、範囲スライス式のコンテキストでは省略できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="b48fa-323">その場合、コンパイラは次の規則を適用して、範囲の目的の区切り記号を推論します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="b48fa-324">たとえば、範囲の開始値を省略した場合、推論される開始値</span><span class="sxs-lookup"><span data-stu-id="b48fa-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="b48fa-325">ステップが指定されていない場合、または指定されたステップが正の場合、は0です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b48fa-326">指定した手順が負の場合に、スライスされた配列の長さから1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="b48fa-327">範囲の終了値を省略した場合、推論された終了値</span><span class="sxs-lookup"><span data-stu-id="b48fa-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="b48fa-328">スライスされた配列の長さ、ステップが指定されていない場合、または指定されたステップが正の場合は1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b48fa-329">指定されたステップが負の場合、は0になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="b48fa-330">配列要素の式</span><span class="sxs-lookup"><span data-stu-id="b48fa-330">Array Element Expressions</span></span>

<span data-ttu-id="b48fa-331">配列式と `Int` 式が指定されている場合は、`[` と `]` 配列要素演算子を使用して新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="b48fa-332">新しい式は、配列の要素型と同じ型になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="b48fa-333">たとえば、`a` が `Double`s の配列にバインドされている場合、`a[4]` は `Double` 式になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="b48fa-334">配列式が単純識別子でない場合は、要素を選択するために、その式をかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="b48fa-335">たとえば、`a` と `b` が両方とも `Int`の配列である場合、連結の要素は次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="b48fa-336">Q # のすべての配列は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b48fa-337">つまり、配列 `a` の最初の要素は常に `a[0]`ます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="b48fa-338">コピーと更新の式</span><span class="sxs-lookup"><span data-stu-id="b48fa-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="b48fa-339">コピーと更新の式を使用して、既存の配列から新しい配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="b48fa-340">コピーおよび更新式は `expression1 w/ expression2 <- expression3`の形式の式です。ここで、`expression1` は `T`型の `T[]` 型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="b48fa-341">2番目の `expression2` は、`expression1` の配列と比較して変更する要素のインデックスを定義し、`Int` 型または `Range`型のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="b48fa-342">`expression2` が `Int`型の場合、`expression3` は `T`型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="b48fa-343">`expression2` が `Range`型の場合、`expression3` は `T[]`型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="b48fa-344">コピーおよび更新式 `arr w/ idx <- value` は、`arr`内の対応する要素に設定されたすべての要素を含む新しい配列を構築します。ただし、`idx`の要素は `value`内の1つの要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="b48fa-345">たとえば、`arr` に配列 `[0,1,2,3]`が含まれている場合、</span><span class="sxs-lookup"><span data-stu-id="b48fa-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="b48fa-346">`arr w/ 0 <- 10` は配列 `[10,1,2,3]`です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="b48fa-347">`arr w/ 2 <- 10` は配列 `[0,1,10,3]`です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="b48fa-348">`arr w/ 0..2..3 <- [10,12]` は配列 `[10,1,12,3]`です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="b48fa-349">ユーザー定義型の名前付き項目についても、同様の式が存在します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="b48fa-350">型の例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="b48fa-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b48fa-351">`Complex(1.,-1.)`型の値が `c` に含まれている場合、`c w/ Re <- 0.` は `Complex(0.,-1.)`に評価される `Complex` 型の式です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="b48fa-352">条件式</span><span class="sxs-lookup"><span data-stu-id="b48fa-352">Conditional Expressions</span></span>

<span data-ttu-id="b48fa-353">同じ型の2つの式とブール式が指定されている場合は、疑問符 `?` と縦棒 `|`を使用して条件式を形成できます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="b48fa-354">たとえば、`a==b ? c | d`します。</span><span class="sxs-lookup"><span data-stu-id="b48fa-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="b48fa-355">この例では、`a==b` が true の場合に条件式の値が `c` され、false の場合は `d` ます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="b48fa-356">2つの式は、入力と出力が同じでも異なる機能をサポートする操作に評価される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="b48fa-357">この場合、条件式の型は、両方の式でサポートされているすべての機能をサポートする入力と出力を持つ操作です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="b48fa-358">たとえば、`Op1`、`Op2`、および `Op3` はすべて `Qubit[]=>Unit`ですが、`Op1` は `Adjoint`をサポートし、`Op2` は両方をサポートします。`Controlled``Op3`</span><span class="sxs-lookup"><span data-stu-id="b48fa-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b48fa-359">`flag ? Op1 | Op2` は `(Qubit[] => Unit)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="b48fa-360">`flag ? Op1 | Op3` は `(Qubit[] => Unit is Adj)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="b48fa-361">`flag ? Op2 | Op3` は `(Qubit[] => Unit is Ctl)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="b48fa-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="b48fa-362">2つの結果式のいずれかに関数呼び出しまたは演算呼び出しが含まれている場合、その呼び出しは、その結果が呼び出しの値になる場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="b48fa-363">たとえば、`a==b ? C(qs) | D(qs)`の場合、`a==b` が true の場合、`C` 操作が呼び出され、false の場合は `D` のみが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="b48fa-364">これは、他の言語のショートサーキットに似ています。</span><span class="sxs-lookup"><span data-stu-id="b48fa-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="b48fa-365">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="b48fa-365">Operator Precedence</span></span>

<span data-ttu-id="b48fa-366">すべての二項演算子は、`^`を除き、右から結合されます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="b48fa-367">角かっこ、`[` および `]`。配列のスライスとインデックス作成では、任意の演算子の前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b48fa-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="b48fa-368">`Adjoint` と `Controlled` は、配列のインデックス作成後、他のすべての演算子の前にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="b48fa-369">演算と関数呼び出しのかっこは、演算子の前、配列のインデックス作成および関数の後にもバインドされます。</span><span class="sxs-lookup"><span data-stu-id="b48fa-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="b48fa-370">演算子は優先順位の高い順になります。</span><span class="sxs-lookup"><span data-stu-id="b48fa-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="b48fa-371">演算子</span><span class="sxs-lookup"><span data-stu-id="b48fa-371">Operator</span></span> | <span data-ttu-id="b48fa-372">アリ</span><span class="sxs-lookup"><span data-stu-id="b48fa-372">Arity</span></span> | <span data-ttu-id="b48fa-373">説明</span><span class="sxs-lookup"><span data-stu-id="b48fa-373">Description</span></span> | <span data-ttu-id="b48fa-374">オペランドの型</span><span class="sxs-lookup"><span data-stu-id="b48fa-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="b48fa-375">`!` の末尾</span><span class="sxs-lookup"><span data-stu-id="b48fa-375">trailing `!`</span></span> | <span data-ttu-id="b48fa-376">単項演算子</span><span class="sxs-lookup"><span data-stu-id="b48fa-376">Unary</span></span> | <span data-ttu-id="b48fa-377">ラップ解除</span><span class="sxs-lookup"><span data-stu-id="b48fa-377">Unwrap</span></span> | <span data-ttu-id="b48fa-378">任意のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="b48fa-378">Any user-defined type</span></span>
 <span data-ttu-id="b48fa-379">`-`、`~~~`、`not`</span><span class="sxs-lookup"><span data-stu-id="b48fa-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="b48fa-380">単項演算子</span><span class="sxs-lookup"><span data-stu-id="b48fa-380">Unary</span></span> | <span data-ttu-id="b48fa-381">負の数値、ビットごとの補数、論理否定</span><span class="sxs-lookup"><span data-stu-id="b48fa-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="b48fa-382">`Int` の `-`、`BigInt`、`~~~`の `Int`、`BigInt` または `Double` `Bool` の `not`</span><span class="sxs-lookup"><span data-stu-id="b48fa-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="b48fa-383">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-383">Binary</span></span> | <span data-ttu-id="b48fa-384">整数の累乗</span><span class="sxs-lookup"><span data-stu-id="b48fa-384">Integer power</span></span> | <span data-ttu-id="b48fa-385">底の `Int` または `BigInt`。指数部は `Int`</span><span class="sxs-lookup"><span data-stu-id="b48fa-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="b48fa-386">`/`、`*`、`%`</span><span class="sxs-lookup"><span data-stu-id="b48fa-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="b48fa-387">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-387">Binary</span></span> | <span data-ttu-id="b48fa-388">除算、乗算、整数剰余</span><span class="sxs-lookup"><span data-stu-id="b48fa-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="b48fa-389">`Int`、`BigInt` または `Double` の `/` と `*`、`Int` `BigInt``%`</span><span class="sxs-lookup"><span data-stu-id="b48fa-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="b48fa-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="b48fa-390">`+`, `-`</span></span> | <span data-ttu-id="b48fa-391">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-391">Binary</span></span> | <span data-ttu-id="b48fa-392">加算または文字列と配列の連結、減算</span><span class="sxs-lookup"><span data-stu-id="b48fa-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="b48fa-393">`Int`、`BigInt` または `Double`、さらに `String` または任意の配列型 `+`</span><span class="sxs-lookup"><span data-stu-id="b48fa-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="b48fa-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="b48fa-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="b48fa-395">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-395">Binary</span></span> | <span data-ttu-id="b48fa-396">左シフト、右シフト</span><span class="sxs-lookup"><span data-stu-id="b48fa-396">Left shift, right shift</span></span> | <span data-ttu-id="b48fa-397">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b48fa-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="b48fa-398">`<`、`<=`、`>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="b48fa-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="b48fa-399">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-399">Binary</span></span> | <span data-ttu-id="b48fa-400">より小さい、より小さい、または等しい、より大きい、より大きい、または等しい比較</span><span class="sxs-lookup"><span data-stu-id="b48fa-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="b48fa-401">`Int`、`BigInt` または `Double`</span><span class="sxs-lookup"><span data-stu-id="b48fa-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="b48fa-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="b48fa-402">`==`, `!=`</span></span> | <span data-ttu-id="b48fa-403">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-403">Binary</span></span> | <span data-ttu-id="b48fa-404">等しい、等しくない比較</span><span class="sxs-lookup"><span data-stu-id="b48fa-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="b48fa-405">任意のプリミティブ型</span><span class="sxs-lookup"><span data-stu-id="b48fa-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="b48fa-406">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-406">Binary</span></span> | <span data-ttu-id="b48fa-407">ビット演算子 AND</span><span class="sxs-lookup"><span data-stu-id="b48fa-407">Bitwise AND</span></span> | <span data-ttu-id="b48fa-408">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b48fa-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="b48fa-409">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-409">Binary</span></span> | <span data-ttu-id="b48fa-410">ビットごとの XOR</span><span class="sxs-lookup"><span data-stu-id="b48fa-410">Bitwise XOR</span></span> | <span data-ttu-id="b48fa-411">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b48fa-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="b48fa-412">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-412">Binary</span></span> | <span data-ttu-id="b48fa-413">ビットごとの OR</span><span class="sxs-lookup"><span data-stu-id="b48fa-413">Bitwise OR</span></span> | <span data-ttu-id="b48fa-414">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b48fa-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="b48fa-415">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-415">Binary</span></span> | <span data-ttu-id="b48fa-416">論理積</span><span class="sxs-lookup"><span data-stu-id="b48fa-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="b48fa-417">Binary</span><span class="sxs-lookup"><span data-stu-id="b48fa-417">Binary</span></span> | <span data-ttu-id="b48fa-418">論理和</span><span class="sxs-lookup"><span data-stu-id="b48fa-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="b48fa-419">Binary/三項</span><span class="sxs-lookup"><span data-stu-id="b48fa-419">Binary/Ternary</span></span> | <span data-ttu-id="b48fa-420">範囲演算子</span><span class="sxs-lookup"><span data-stu-id="b48fa-420">Range operator</span></span> | `Int`
 <span data-ttu-id="b48fa-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="b48fa-421">`?` `|`</span></span> | <span data-ttu-id="b48fa-422">三項</span><span class="sxs-lookup"><span data-stu-id="b48fa-422">Ternary</span></span> | <span data-ttu-id="b48fa-423">条件付き</span><span class="sxs-lookup"><span data-stu-id="b48fa-423">Conditional</span></span> | <span data-ttu-id="b48fa-424">左側のの `Bool`</span><span class="sxs-lookup"><span data-stu-id="b48fa-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="b48fa-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="b48fa-425">`w/` `<-`</span></span> | <span data-ttu-id="b48fa-426">三項</span><span class="sxs-lookup"><span data-stu-id="b48fa-426">Ternary</span></span> | <span data-ttu-id="b48fa-427">コピーと更新</span><span class="sxs-lookup"><span data-stu-id="b48fa-427">Copy-and-update</span></span> | <span data-ttu-id="b48fa-428">「[コピーと更新の式」を](#copy-and-update-expressions)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48fa-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
