---
title: Q の型式#
description: 'Q # の式として、定数、変数、演算子、操作、関数を指定、参照、および結合する方法について説明します。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431208"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="d8cbb-103">Q の型式#</span><span class="sxs-lookup"><span data-stu-id="d8cbb-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="d8cbb-104">数値式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-104">Numeric Expressions</span></span>

<span data-ttu-id="d8cbb-105">数値式は `Int` 、、 `BigInt` 、または型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="d8cbb-106">つまり、整数または浮動小数点数のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="d8cbb-107">`Int`Q # のリテラルは、単に一連の数字として記述されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="d8cbb-108">16進数とバイナリ整数は、それぞれとプレフィックスでサポートされてい `0x` `0b` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="d8cbb-109">`BigInt`Q # のリテラルは、末尾またはサフィックスを使用して書き込まれ `l` `L` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="d8cbb-110">16進数の大きな整数は、プレフィックス "0x" でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="d8cbb-111">したがって、リテラルの有効な使用法は次のとおりです `BigInt` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="d8cbb-112">`Double`Q # のリテラルは、10進数を使用して記述された浮動小数点数です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="d8cbb-113">小数点、、または指数部を使用して記述でき `.` ます。 "e" または "e" で示されます (その後は、負の符号と小数点以下の桁数のみが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="d8cbb-114">有効なリテラルは、、 `Double` `0.0` `1.2e5` 、 `1e-5` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="d8cbb-115">任意の要素型の配列式が指定されて `Int` いる場合、組み込み関数を使用して式を作成できます。その際、 [`Length`](xref:microsoft.quantum.core.length) かっこで囲まれた配列式を使用し `(` `)` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="d8cbb-116">たとえば、 `a` が配列にバインドされている場合、 `Length(a)` は整数式になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="d8cbb-117">`b`が整数の配列の配列である場合 `Int[][]` 、は `Length(b)` のサブ配列の数です `b` `Length(b[1])` 。はの2番目のサブ配列の整数の数です `b` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="d8cbb-118">同じ型の2つの数値式が指定されている場合、二項演算子 `+` 、 `-` 、、およびを使用して、 `*` `/` 新しい数値式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="d8cbb-119">新しい式の型は、構成式の型と同じになります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="d8cbb-120">2つの整数式を指定すると、2項演算子 `^` (power) を使用して新しい整数式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="d8cbb-121">同様に、 `^` 2 つの double 式を使用して、新しい double 式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="d8cbb-122">最後に、 `^` 新しい大きな整数式を作成するために、左側に大きな整数と右側に整数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="d8cbb-123">この場合、2番目のパラメーターは32ビットにする必要があります。それ以外の場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="d8cbb-124">2つの整数または整数式が指定されている場合、新しい整数または大きな整数式は、 `%` (剰余)、 `&&&` (ビット演算 and)、 `|||` (ビットごとの or)、または `^^^` (ビットごとの XOR) 演算子を使用して形成されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="d8cbb-125">左側に整数または整数式を指定し、右側に整数式を指定すると、 `<<<` (算術左シフト) 演算子または `>>>` (算術右シフト) 演算子を使用して、左側の式と同じ型の新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="d8cbb-126">シフト演算の2番目のパラメーター (シフト量) は、0以上である必要があります。負のシフト量の動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="d8cbb-127">また、いずれかのシフト操作のシフト量は、32ビットにも適合する必要があります。それ以外の場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="d8cbb-128">シフトする数値が整数である場合は、シフトの量が解釈されます `mod 64` 。つまり、シフト1と65のシフトは同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="d8cbb-129">整数値と大きな整数値の両方に対して、シフトは算術演算です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="d8cbb-130">負の値を左または右にシフトすると、負の数値になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="d8cbb-131">つまり、1つのステップを左または右にシフトすることは、それぞれ2で乗算または除算するのとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="d8cbb-132">整数の除算と整数の剰余は、C# と同じ負の数値の動作に従います。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="d8cbb-133">つまり、 `a % b` は常にと同じ符号を持ち、常に同じになり `a` `b * (a / b) + a % b` `a` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="d8cbb-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="d8cbb-135">5</span><span class="sxs-lookup"><span data-stu-id="d8cbb-135">5</span></span> | <span data-ttu-id="d8cbb-136">2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-136">2</span></span> | <span data-ttu-id="d8cbb-137">2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-137">2</span></span> | <span data-ttu-id="d8cbb-138">1</span><span class="sxs-lookup"><span data-stu-id="d8cbb-138">1</span></span>
 <span data-ttu-id="d8cbb-139">5</span><span class="sxs-lookup"><span data-stu-id="d8cbb-139">5</span></span> | <span data-ttu-id="d8cbb-140">-2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-140">-2</span></span> | <span data-ttu-id="d8cbb-141">-2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-141">-2</span></span> | <span data-ttu-id="d8cbb-142">1</span><span class="sxs-lookup"><span data-stu-id="d8cbb-142">1</span></span>
 <span data-ttu-id="d8cbb-143">-5</span><span class="sxs-lookup"><span data-stu-id="d8cbb-143">-5</span></span> | <span data-ttu-id="d8cbb-144">2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-144">2</span></span> | <span data-ttu-id="d8cbb-145">-2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-145">-2</span></span> | <span data-ttu-id="d8cbb-146">-1</span><span class="sxs-lookup"><span data-stu-id="d8cbb-146">-1</span></span>
 <span data-ttu-id="d8cbb-147">-5</span><span class="sxs-lookup"><span data-stu-id="d8cbb-147">-5</span></span> | <span data-ttu-id="d8cbb-148">-2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-148">-2</span></span> | <span data-ttu-id="d8cbb-149">2</span><span class="sxs-lookup"><span data-stu-id="d8cbb-149">2</span></span> | <span data-ttu-id="d8cbb-150">-1</span><span class="sxs-lookup"><span data-stu-id="d8cbb-150">-1</span></span>

<span data-ttu-id="d8cbb-151">大規模な整数除算と剰余は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="d8cbb-152">数値式を指定すると、単項演算子を使用して新しい式を作成でき `-` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="d8cbb-153">新しい式は、構成式と同じ型になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="d8cbb-154">整数型または整数型の式が指定されている場合は、 `~~~` (ビットごとの補数) 単項演算子を使用して、同じ型の新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="d8cbb-155">ブール式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-155">Boolean Expressions</span></span>

<span data-ttu-id="d8cbb-156">2つの `Bool` リテラル値は、 `true` と `false` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="d8cbb-157">同じプリミティブ型の2つの式がある場合、 `==` および `!=` 二項演算子を使用して式を作成でき `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="d8cbb-158">2つの式が等しい場合、式は true になり、そうでない場合は false になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="d8cbb-159">ユーザー定義型の値を比較することはできません。ラップ解除された値だけを比較できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="d8cbb-160">たとえば、"ラップ解除" 演算子を使用します `!` (「 [Q # の型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)」で詳しく説明しています)。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="d8cbb-161">値の等価比較 `Qubit` は、id の等価性を表します。つまり、2つの式が同じ qubit を識別するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="d8cbb-162">2つの qubits の状態は、この比較によって比較、アクセス、測定、または変更されません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="d8cbb-163">`Double`丸め効果が原因で、値の等価比較が誤解される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="d8cbb-164">たとえば、のように `49.0 * (1.0/49.0) != 1.0` なります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="d8cbb-165">2つの数値式を指定すると、二項演算子 `>` 、 `<` 、、およびを使用して、 `>=` `<=` 新しいブール式を作成できます。この式は、最初の式の値が、2番目の式の値よりも大きい、より小さい、より大きい、または等しい場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="d8cbb-166">2つのブール式が指定されている `and` `or` 場合、二項演算子と二項演算子を使用すると、2つの式の両方 (resp または両方) が true の場合に true になる新しいブール式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="d8cbb-167">任意のブール式を指定した `not` 場合、単項演算子を使用して新しいブール式を作成できます。これは、構成式が false の場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="d8cbb-168">文字列式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-168">String Expressions</span></span>

<span data-ttu-id="d8cbb-169">Q # では、 `fail` ステートメント ([制御フロー](xref:microsoft.quantum.guide.controlflow#fail-statement)で説明) および標準関数で文字列を使用でき [`Message`](xref:microsoft.quantum.intrinsic.message) ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="d8cbb-170">後者の特定の動作は、使用されているシミュレーターによって異なりますが、通常、Q # プログラム中に呼び出されると、メッセージはホストコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="d8cbb-171">Q # の文字列は、リテラルまたは挿入文字列です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="d8cbb-172">文字列リテラルは、ほとんどの言語の単純な文字列リテラルに似ています。これは、二重引用符で囲まれた Unicode 文字のシーケンス `"` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="d8cbb-173">文字列の内部では、円記号を使用して二重引用符をエスケープし、改行文字をとして、キャリッジリターンをとして、タブをとして `\` 挿入でき `\n` `\r` `\t` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="d8cbb-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="d8cbb-175">挿入文字列</span><span class="sxs-lookup"><span data-stu-id="d8cbb-175">Interpolated strings</span></span>

<span data-ttu-id="d8cbb-176">文字列補間の Q # 構文は C# 構文のサブセットですが、ここでは Q # に関連する重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="d8cbb-177">主な違いについては、以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="d8cbb-178">文字列リテラルを挿入文字列として識別するため、先頭に `$` の記号を追加してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="d8cbb-179">との間には、 `$` `"` 文字列リテラルを開始する空白を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="d8cbb-180">次に示すのは、関数を使用して、 [`Message`](xref:microsoft.quantum.intrinsic.message) 他の Q # 式と共に測定の結果をコンソールに書き込む基本的な例です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="d8cbb-181">有効な Q # 式は、挿入文字列に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="d8cbb-182">C# 構文の詳細については、「挿入[*文字列*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="d8cbb-183">最も重要な違いは、Q # では逐語的 (複数行) の補間文字列がサポートされないことです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="d8cbb-184">挿入文字列内の式は、C# 構文ではなく、Q # 構文に従います。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="d8cbb-185">範囲の式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-185">Range Expressions</span></span>

<span data-ttu-id="d8cbb-186">`Int`、、およびという3つの式がある場合、は、 `start` `step` `stop` `start .. step .. stop` が渡されるまで、最初の要素が `start` 、2番目の要素が、 `start+step` 3 番目の要素がである範囲式です `start+step+step` 。 `stop`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="d8cbb-187">たとえば、が正の値またはの場合、範囲は空になることがあり `step` `stop < start` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="d8cbb-188">との間の差がの整数の倍数である場合、範囲の最後の要素はになります `stop` `start` `stop` `step` 。つまり、範囲は両端を含みます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="d8cbb-189">2 `Int` つの式とが指定されて `start` `stop` いる場合、 `start .. stop` はと等しい範囲式です `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="d8cbb-190">がより小さい場合でも、暗黙のは + 1 であることに注意して `step` `stop` `start` ください。この場合、範囲は空になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="d8cbb-191">範囲の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-191">Some example ranges are:</span></span>

- <span data-ttu-id="d8cbb-192">`1..3`の範囲は1、2、3です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="d8cbb-193">`2..2..5`は2、4の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="d8cbb-194">`2..2..6`は2、4、6の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="d8cbb-195">`6..-2..2`は6、4、2の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="d8cbb-196">`2..1`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="d8cbb-197">`2..6..7`は2の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="d8cbb-198">`2..2..1`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="d8cbb-199">`1..-1..2`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="d8cbb-200">Qubit 式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-200">Qubit Expressions</span></span>

<span data-ttu-id="d8cbb-201">唯一の `Qubit` 式は、 `Qubit` 配列の値または配列要素にバインドされている記号です `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="d8cbb-202">リテラルがありません `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="d8cbb-203">P# li 式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-203">Pauli Expressions</span></span>

<span data-ttu-id="d8cbb-204">、、、およびの4つの `Pauli` 値 `PauliI` は、 `PauliX` `PauliY` `PauliZ` すべて有効な `Pauli` 式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="d8cbb-205">それ以外の式は、 `Pauli` `Pauli` 配列の値または配列要素にバインドされるシンボルです `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="d8cbb-206">結果式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-206">Result Expressions</span></span>

<span data-ttu-id="d8cbb-207">2つの `Result` 値 ( `One` と `Zero` ) は、有効な `Result` 式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="d8cbb-208">それ以外の式は、 `Result` `Result` 配列の値または配列要素にバインドされるシンボルです `Result` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="d8cbb-209">特に、 `One` は整数と同じではなく、 `1` これらの間に直接変換がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="d8cbb-210">とにも同じことが当てはまり `Zero` `0` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="d8cbb-211">タプル式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-211">Tuple Expressions</span></span>

<span data-ttu-id="d8cbb-212">組リテラルは、とで囲まれた、コンマで区切られた適切な型の要素式のシーケンスです `(` `)` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="d8cbb-213">たとえば、 `(1, One)` は `(Int, Result)` 式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="d8cbb-214">リテラル以外の唯一のタプル式は、タプル値にバインドされたシンボル、組配列の配列要素、およびタプルを返す呼び出し可能な呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="d8cbb-215">ユーザー定義型の式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="d8cbb-216">ユーザー定義型のリテラルは、型名の後に型の基本タプル型のタプルリテラルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="d8cbb-217">たとえば、 `IntPair` がに基づくユーザー定義型である場合、は `(Int, Int)` `IntPair(2, 3)` その型の有効なリテラルになります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="d8cbb-218">リテラル以外に、ユーザー定義型の唯一の式は、その型の値、その型の配列の配列要素、およびその型を返す呼び出し可能な呼び出しの値にバインドされている記号です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="d8cbb-219">ラップ解除 (式の)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-219">Unwrap Expressions</span></span>

<span data-ttu-id="d8cbb-220">Q # では、ラップ解除演算子は末尾の感嘆符 `!` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="d8cbb-221">たとえば、 `IntPair` が基になる型のユーザー定義型で、が `(Int, Int)` `s` 値を持つ変数である場合、はになり `IntPair(2, 3)` `s!` `(2, 3)` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="d8cbb-222">他のユーザー定義型の観点から定義されたユーザー定義型の場合。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="d8cbb-223">ラップ解除演算子は、繰り返すことができます。たとえば、は、 `s!!` の二重ラップ解除された値を示し `s` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="d8cbb-224">したがって、 `WrappedPair` が基になる型のユーザー定義型で、 `IntPair` `t` が値を持つ変数である場合、はになり `WrappedPair(IntPair(1,2))` `t!!` `(1,2)` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="d8cbb-225">演算子は、 `!` 配列のインデックス作成およびスライス以外の他のすべての演算子よりも優先順位が高く `[]` なります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="d8cbb-226">`!`とをバインドします。つまり `[]` 、 `a[i]![3]` `((a[i])!)[3]` `i` の ' th 要素を受け取り、ラップを解除してから、ラップ解除され `a` た値の3番目の要素 (配列である必要があります) を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="d8cbb-227">演算子の優先順位は、 `!` 明らかでない可能性がある1つの影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="d8cbb-228">関数または操作が、ラップされていない値を返す場合は、ラップ解除ではなく、引数のタプルが呼び出しにバインドされるように、関数または操作の呼び出しをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="d8cbb-229">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="d8cbb-230">配列式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-230">Array Expressions</span></span>

<span data-ttu-id="d8cbb-231">配列リテラルは、およびで囲まれた、コンマで区切られた1つ以上の要素式のシーケンスです `[` `]` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="d8cbb-232">すべての要素は、同じ型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-232">All elements must be compatible with the same type.</span></span>


<span data-ttu-id="d8cbb-233">同じ型の2つの配列を指定した場合、 `+` 2 つの配列を連結した新しい配列を作成するために二項演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="d8cbb-234">たとえば、 `[1,2,3] + [4,5,6]` は `[1,2,3,4,5,6]` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="d8cbb-235">配列の作成</span><span class="sxs-lookup"><span data-stu-id="d8cbb-235">Array Creation</span></span>

<span data-ttu-id="d8cbb-236">型と式を指定した場合、演算子を使用して、指定された `Int` `new` サイズの新しい配列を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="d8cbb-237">たとえば、では、 `new Int[i + 1]` `Int` 要素を含む新しい配列が割り当てら `i + 1` れます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="d8cbb-238">新しい配列の要素は、型に依存する既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-238">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="d8cbb-239">ほとんどの場合、これはゼロのバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-239">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="d8cbb-240">エンティティへの参照である qubits と callables 指定できる場合、適切な既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-240">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="d8cbb-241">したがって、これらの型では、既定値は無効な参照で、ランタイムエラーを発生させずに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-241">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="d8cbb-242">これは、C# や Java などの言語での null 参照に似ています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-242">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="d8cbb-243">Qubits または callables 含む配列は、要素が安全に使用される前に、既定値以外の値で適切に初期化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-243">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="d8cbb-244">適切な初期化ルーチンについては、「」を参照 <xref:microsoft.quantum.arrays> してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-244">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="d8cbb-245">各型の既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-245">The default values for each type are:</span></span>

<span data-ttu-id="d8cbb-246">Type</span><span class="sxs-lookup"><span data-stu-id="d8cbb-246">Type</span></span> | <span data-ttu-id="d8cbb-247">Default</span><span class="sxs-lookup"><span data-stu-id="d8cbb-247">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="d8cbb-248">_無効な qubit_</span><span class="sxs-lookup"><span data-stu-id="d8cbb-248">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="d8cbb-249">空の範囲。`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-249">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="d8cbb-250">_無効な呼び出し可能_</span><span class="sxs-lookup"><span data-stu-id="d8cbb-250">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="d8cbb-251">タプル型は要素ごとに初期化されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-251">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="d8cbb-252">配列要素</span><span class="sxs-lookup"><span data-stu-id="d8cbb-252">Array Elements</span></span>

<span data-ttu-id="d8cbb-253">配列式と式が指定されて `Int` いる場合は、 `[` との配列要素演算子を使用して新しい式を作成でき `]` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-253">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="d8cbb-254">新しい式は、配列の要素型と同じ型になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-254">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="d8cbb-255">たとえば、 `a` がの配列にバインドされている場合、 `Double` `a[4]` は `Double` 式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-255">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="d8cbb-256">配列式が単純識別子でない場合は、要素を選択するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-256">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="d8cbb-257">たとえば、 `a` と `b` が両方ともの配列である場合、 `Int` 連結の要素は次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-257">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="d8cbb-258">Q # のすべての配列は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-258">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="d8cbb-259">つまり、配列の最初の要素 `a` は常に `a[0]` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-259">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="d8cbb-260">配列スライス</span><span class="sxs-lookup"><span data-stu-id="d8cbb-260">Array Slices</span></span>

<span data-ttu-id="d8cbb-261">配列式と式が指定されて `Range` いる場合は、 `[` およびの配列スライス演算子を使用して新しい式を作成でき `]` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-261">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="d8cbb-262">新しい式は配列と同じ型になり、の要素によってインデックス付けされた配列項目がによって定義された順序で格納され `Range` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-262">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="d8cbb-263">たとえば、 `a` がの配列にバインドされている場合、 `Double` `a[3..-1..0]` は `Double[]` の最初の4つの要素を含む式ですが、 `a` では逆の順序で表示され `a` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-263">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="d8cbb-264">が空の場合、結果とし `Range` て得られる配列スライスは長さが0になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-264">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="d8cbb-265">配列要素を参照する場合と同様に、配列式が単純識別子でない場合は、スライスするためにかっこを囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-265">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="d8cbb-266">`a`と `b` がの両方の配列の場合 `Int` 、連結のスライスは次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-266">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="d8cbb-267">推定される開始/終了値</span><span class="sxs-lookup"><span data-stu-id="d8cbb-267">Inferred start/end values</span></span>

<span data-ttu-id="d8cbb-268">0.8 リリース以降では、範囲スライスのコンテキスト式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-268">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="d8cbb-269">特に、範囲の開始値と終了値は、範囲スライス式のコンテキストでは省略できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-269">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="d8cbb-270">その場合、コンパイラは次の規則を適用して、範囲の目的の区切り記号を推論します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-270">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="d8cbb-271">たとえば、範囲の開始値を省略した場合、推論される開始値</span><span class="sxs-lookup"><span data-stu-id="d8cbb-271">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="d8cbb-272">ステップが指定されていない場合、または指定されたステップが正の場合、は0です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-272">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="d8cbb-273">指定した手順が負の場合に、スライスされた配列の長さから1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-273">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="d8cbb-274">範囲の終了値を省略した場合、推論された終了値</span><span class="sxs-lookup"><span data-stu-id="d8cbb-274">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="d8cbb-275">スライスされた配列の長さ、ステップが指定されていない場合、または指定されたステップが正の場合は1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-275">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="d8cbb-276">指定されたステップが負の場合、は0になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-276">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="d8cbb-277">コピーと更新の式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-277">Copy-and-Update Expressions</span></span>

<span data-ttu-id="d8cbb-278">すべての Q # 型は値型であるため、qubits は多少特別な役割を持ちます。つまり、値がシンボルにバインドされたとき、またはシンボルが再バインドされたときに、正式に "コピー" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-278">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="d8cbb-279">つまり、Q # の動作は、割り当て時にコピーが作成された場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-279">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="d8cbb-280">もちろん、実際には、関連する部分のみが必要に応じて再作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-280">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="d8cbb-281">これには、配列も含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-281">This in particular also includes arrays.</span></span>
<span data-ttu-id="d8cbb-282">特に、配列項目を更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-282">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="d8cbb-283">既存の配列を変更するには、*コピーと更新*のメカニズムを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-283">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="d8cbb-284">*コピーと更新の*式を使用して、既存の配列から新しい配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-284">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="d8cbb-285">コピーおよび更新式は、形式の式です `expression1 w/ expression2 <- expression3` 。ここで、 `expression1` は何らかの型の型である必要があり `T[]` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-285">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="d8cbb-286">2番目のは、の `expression2` 配列と比較して変更する要素のインデックスを定義し、型 `expression1` または型のいずれかである必要があり `Int` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-286">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="d8cbb-287">が型である場合、は型である `expression2` `Int` `expression3` 必要があり `T` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-287">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="d8cbb-288">が型である場合、は型である `expression2` `Range` `expression3` 必要があり `T[]` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-288">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="d8cbb-289">コピーおよび更新式は、の要素に設定 `arr w/ idx <- value` されているすべての要素を含む新しい配列を構築し `arr` ます。ただし、の要素は、の `idx` 1 つのに設定され `value` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-289">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="d8cbb-290">たとえば、に `arr` 配列が含まれている場合、 `[0,1,2,3]`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-290">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="d8cbb-291">`arr w/ 0 <- 10`は配列 `[10,1,2,3]` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-291">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="d8cbb-292">`arr w/ 2 <- 10`は配列 `[0,1,10,3]` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-292">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="d8cbb-293">`arr w/ 0..2..3 <- [10,12]`は配列 `[10,1,12,3]` です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-293">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="d8cbb-294">名前付き項目のコピーと更新の式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-294">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="d8cbb-295">ユーザー定義型の名前付き項目についても、同様の式が存在します。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-295">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="d8cbb-296">型の例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-296">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="d8cbb-297">`c`に型の値が含まれている場合 `Complex(1., -1.)` 、 `c w/ Re <- 0.` はに評価される型の式です `Complex` `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-297">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="d8cbb-298">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="d8cbb-298">Jagged Arrays</span></span>

<span data-ttu-id="d8cbb-299">ジャグ配列は、"配列の配列" と呼ばれることもあり、要素が配列である配列です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-299">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="d8cbb-300">ジャグ配列の要素のサイズは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-300">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="d8cbb-301">次の例は、乗算テーブルを表すジャグ配列を宣言および初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-301">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="d8cbb-302">呼び出し許容の配列</span><span class="sxs-lookup"><span data-stu-id="d8cbb-302">Arrays of callables</span></span> 

<span data-ttu-id="d8cbb-303">呼び出し可能な型の詳細については、次のページ「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-303">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="d8cbb-304">共通の要素型が演算型または関数型である場合、すべての要素の入力と出力の型が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-304">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="d8cbb-305">配列の要素型は、すべての要素でサポートされているすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-305">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="d8cbb-306">たとえば、、 `Op1` `Op2` 、およびはすべてですが、はをサポートし、サポートし、 `Op3` `Qubit[] => Unit` 両方を `Op1` `Adjoint` `Op2` `Controlled` `Op3` サポートします。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-306">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="d8cbb-307">`[Op1, Op2]`は操作の配列です `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-307">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="d8cbb-308">`[Op1, Op3]`は操作の配列です `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-308">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="d8cbb-309">`[Op2, Op3]`は操作の配列です `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-309">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="d8cbb-310">空の配列リテラル `[]` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-310">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="d8cbb-311">で `new ★[0]` はなく、 `★` 適切な型のプレースホルダーとしてを使用すると、は、必要な長さゼロの配列を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-311">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="d8cbb-312">条件式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-312">Conditional Expressions</span></span>

<span data-ttu-id="d8cbb-313">同じ型の2つの式とブール式が指定されている場合は、疑問符と縦棒を使用して条件式を形成でき `?` `|` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-313">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="d8cbb-314">たとえば、のように `a==b ? c | d` なります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-314">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="d8cbb-315">この例では、が true で、かつ false の場合、条件式の値はになり `c` `a==b` `d` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-315">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="d8cbb-316">呼び出しが許容される条件式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-316">Conditional expressions with callables</span></span>

<span data-ttu-id="d8cbb-317">2つの式は、入力と出力が同じでも異なる機能をサポートする操作に評価される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-317">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="d8cbb-318">この場合、条件式の型は、両方の式でサポートされているすべての機能をサポートする入力と出力を持つ操作です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-318">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="d8cbb-319">たとえば、、 `Op1` `Op2` 、およびはすべてですが、はをサポートし、サポートし、 `Op3` `Qubit[]=>Unit` 両方を `Op1` `Adjoint` `Op2` `Controlled` `Op3` サポートします。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-319">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="d8cbb-320">`flag ? Op1 | Op2`は `(Qubit[] => Unit)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-320">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="d8cbb-321">`flag ? Op1 | Op3`は `(Qubit[] => Unit is Adj)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-321">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="d8cbb-322">`flag ? Op2 | Op3`は `(Qubit[] => Unit is Ctl)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-322">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="d8cbb-323">2つの結果式のいずれかに関数呼び出しまたは演算呼び出しが含まれている場合、その呼び出しは、その結果が呼び出しの値になる場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-323">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="d8cbb-324">たとえば、 `a==b ? C(qs) | D(qs)` が true の場合、操作が呼び出されます。 false の場合は、 `a==b` のみが呼び出され `C` `D` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-324">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="d8cbb-325">これは、他の言語のショートサーキットに似ています。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-325">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="d8cbb-326">呼び出し可能式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-326">Callable Expressions</span></span>

<span data-ttu-id="d8cbb-327">呼び出し可能なリテラルは、コンパイルスコープで定義されている操作または関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-327">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="d8cbb-328">たとえば、 `X` は、標準ライブラリの操作を参照する操作リテラルであり、 `X` `Message` は標準ライブラリ関数を参照する関数リテラルです `Message` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-328">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="d8cbb-329">操作が `Adjoint` ファンクタをサポートする場合、 `Adjoint op` は演算式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-329">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="d8cbb-330">同様に、操作がファンクタをサポートする場合、 `Controlled` `Controlled op` は演算式です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-330">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="d8cbb-331">これらの式の型は、[呼び出し操作の特殊化](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)時に指定されます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-331">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="d8cbb-332">ファンクター ( `Adjoint` および `Controlled` ) は、ラップ解除演算子 `!` および [] での配列インデックス作成を除き、他のすべての演算子よりも密接にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-332">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="d8cbb-333">このため、操作で使用されている機能がサポートされていれば、次のすべての処理が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-333">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="d8cbb-334">型パラメーター化可能な呼び出し可能式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-334">Type-parameterized callable expressions</span></span>

<span data-ttu-id="d8cbb-335">呼び出し可能なリテラルは、値として使用できます。たとえば、変数に代入する場合や、別の呼び出し可能に渡す場合です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-335">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="d8cbb-336">この場合、呼び出し可能な[型パラメーター](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)がある場合は、呼び出し可能な値の一部として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-336">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="d8cbb-337">呼び出し可能な値には、指定されていない型パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-337">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="d8cbb-338">たとえば、 `Fun` がシグネチャを持つ関数の場合は、次のようになり `'T1->Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-338">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="d8cbb-339">呼び出し可能呼び出し式</span><span class="sxs-lookup"><span data-stu-id="d8cbb-339">Callable Invocation Expressions</span></span>

<span data-ttu-id="d8cbb-340">呼び出し可能なシグネチャの入力型の呼び出し可能な (操作または関数) 式と組式が指定されている場合、呼び出し式は、呼び出し可能な式にタプル式を追加することによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-340">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="d8cbb-341">呼び出し式の型は、呼び出し可能なシグネチャの出力型です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-341">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="d8cbb-342">たとえば、 `Op` がシグネチャを持つ操作である場合、 `((Int, Qubit) => Double)` `Op(3, qubit1)` は型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-342">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="d8cbb-343">同様に、 `Sin` がシグネチャを持つ関数の場合、 `(Double -> Double)` `Sin(0.1)` は型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-343">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="d8cbb-344">最後に、 `Builder` がシグネチャを持つ関数の場合、 `(Int -> (Int -> Int))` `Builder(3)` は Into から Int への関数になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-344">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="d8cbb-345">呼び出し可能な値の式の結果を呼び出すには、呼び出し可能な式を囲むかっこのペアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-345">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="d8cbb-346">したがって、前の段落からを呼び出した結果を呼び出すに `Builder` は、正しい構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-346">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="d8cbb-347">[型パラメーター](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)の呼び出し可能な呼び出しを呼び出すときに、実際の型パラメーターを山かっこ内 `<` および呼び出し可能な `>` 式の後に指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-347">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="d8cbb-348">これは通常、Q # コンパイラによって実際の型が推論されるため、不要です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-348">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="d8cbb-349">ただし、型パラメーターの引数が指定されていない*場合は、* [部分的なアプリケーション](xref:microsoft.quantum.guide.operationsfunctions#partial-application)で必要になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-349">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="d8cbb-350">また、異なるファンのサポートを持つ操作を呼び出し可能に渡す場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-350">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="d8cbb-351">たとえば、にシグネチャがあり、シグネチャを持ち、シグネチャを持つ場合、2番目の引数としてを呼び出し、3番目の引数としてを `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` 呼び出し `Func` `Op1` `Op2` `Op3` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-351">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="d8cbb-352">との型が異なるため、型指定が必要です。そのため、 `Op3` `Op1` コンパイラはこれを仕様なしにあいまいとして扱います。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-352">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="d8cbb-353">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d8cbb-353">Operator Precedence</span></span>

<span data-ttu-id="d8cbb-354">すべての二項演算子は、を除き、右から結合され `^` ます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-354">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="d8cbb-355">角かっこは、 `[` `]` 配列のスライスとインデックス作成のために、任意の演算子の前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-355">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="d8cbb-356">`Adjoint` `Controlled` 配列のインデックス作成後、他のすべての演算子の前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-356">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="d8cbb-357">演算と関数呼び出しのかっこは、演算子の前、配列のインデックス作成および関数の後にもバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-357">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="d8cbb-358">演算子は優先順位の高い順になります。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-358">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="d8cbb-359">演算子</span><span class="sxs-lookup"><span data-stu-id="d8cbb-359">Operator</span></span> | <span data-ttu-id="d8cbb-360">アリ</span><span class="sxs-lookup"><span data-stu-id="d8cbb-360">Arity</span></span> | <span data-ttu-id="d8cbb-361">説明</span><span class="sxs-lookup"><span data-stu-id="d8cbb-361">Description</span></span> | <span data-ttu-id="d8cbb-362">オペランドの型</span><span class="sxs-lookup"><span data-stu-id="d8cbb-362">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="d8cbb-363">末尾`!`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-363">trailing `!`</span></span> | <span data-ttu-id="d8cbb-364">単項</span><span class="sxs-lookup"><span data-stu-id="d8cbb-364">Unary</span></span> | <span data-ttu-id="d8cbb-365">ラップ解除</span><span class="sxs-lookup"><span data-stu-id="d8cbb-365">Unwrap</span></span> | <span data-ttu-id="d8cbb-366">任意のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="d8cbb-366">Any user-defined type</span></span>
 <span data-ttu-id="d8cbb-367">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-367">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="d8cbb-368">単項</span><span class="sxs-lookup"><span data-stu-id="d8cbb-368">Unary</span></span> | <span data-ttu-id="d8cbb-369">負の数値、ビットごとの補数、論理否定</span><span class="sxs-lookup"><span data-stu-id="d8cbb-369">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="d8cbb-370">`Int`、、 `BigInt` またはの場合 `Double` `-` `Int` は `BigInt` `~~~` `Bool` 、の場合は。`not`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-370">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="d8cbb-371">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-371">Binary</span></span> | <span data-ttu-id="d8cbb-372">整数の累乗</span><span class="sxs-lookup"><span data-stu-id="d8cbb-372">Integer power</span></span> | <span data-ttu-id="d8cbb-373">`Int`底の場合は `BigInt` 、 `Int` 指数部の場合は</span><span class="sxs-lookup"><span data-stu-id="d8cbb-373">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="d8cbb-374">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-374">`/`, `*`, `%`</span></span> | <span data-ttu-id="d8cbb-375">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-375">Binary</span></span> | <span data-ttu-id="d8cbb-376">除算、乗算、整数剰余</span><span class="sxs-lookup"><span data-stu-id="d8cbb-376">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="d8cbb-377">`Int`、、、、 `BigInt` `Double` `/` `*` `Int` または `BigInt` の場合は。`%`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-377">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="d8cbb-378">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-378">`+`, `-`</span></span> | <span data-ttu-id="d8cbb-379">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-379">Binary</span></span> | <span data-ttu-id="d8cbb-380">加算または文字列と配列の連結、減算</span><span class="sxs-lookup"><span data-stu-id="d8cbb-380">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="d8cbb-381">`Int`、、 `BigInt` また `Double` は、また `String` はのいずれかの配列型`+`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-381">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="d8cbb-382">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-382">`<<<`, `>>>`</span></span> | <span data-ttu-id="d8cbb-383">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-383">Binary</span></span> | <span data-ttu-id="d8cbb-384">左シフト、右シフト</span><span class="sxs-lookup"><span data-stu-id="d8cbb-384">Left shift, right shift</span></span> | <span data-ttu-id="d8cbb-385">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-385">`Int` or `BigInt`</span></span>
 <span data-ttu-id="d8cbb-386">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-386">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="d8cbb-387">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-387">Binary</span></span> | <span data-ttu-id="d8cbb-388">より小さい、より小さい、または等しい、より大きい、より大きい、または等しい比較</span><span class="sxs-lookup"><span data-stu-id="d8cbb-388">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="d8cbb-389">`Int`、、 `BigInt` または`Double`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-389">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="d8cbb-390">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-390">`==`, `!=`</span></span> | <span data-ttu-id="d8cbb-391">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-391">Binary</span></span> | <span data-ttu-id="d8cbb-392">等しい、等しくない比較</span><span class="sxs-lookup"><span data-stu-id="d8cbb-392">equal, not-equal comparisons</span></span> | <span data-ttu-id="d8cbb-393">任意のプリミティブ型</span><span class="sxs-lookup"><span data-stu-id="d8cbb-393">any primitive type</span></span>
 `&&&` | <span data-ttu-id="d8cbb-394">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-394">Binary</span></span> | <span data-ttu-id="d8cbb-395">ビット演算子 AND</span><span class="sxs-lookup"><span data-stu-id="d8cbb-395">Bitwise AND</span></span> | <span data-ttu-id="d8cbb-396">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-396">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="d8cbb-397">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-397">Binary</span></span> | <span data-ttu-id="d8cbb-398">ビットごとの XOR</span><span class="sxs-lookup"><span data-stu-id="d8cbb-398">Bitwise XOR</span></span> | <span data-ttu-id="d8cbb-399">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-399">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="d8cbb-400">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-400">Binary</span></span> | <span data-ttu-id="d8cbb-401">ビットごとの OR</span><span class="sxs-lookup"><span data-stu-id="d8cbb-401">Bitwise OR</span></span> | <span data-ttu-id="d8cbb-402">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-402">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="d8cbb-403">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-403">Binary</span></span> | <span data-ttu-id="d8cbb-404">論理積</span><span class="sxs-lookup"><span data-stu-id="d8cbb-404">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="d8cbb-405">Binary</span><span class="sxs-lookup"><span data-stu-id="d8cbb-405">Binary</span></span> | <span data-ttu-id="d8cbb-406">論理和</span><span class="sxs-lookup"><span data-stu-id="d8cbb-406">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="d8cbb-407">Binary/三項</span><span class="sxs-lookup"><span data-stu-id="d8cbb-407">Binary/Ternary</span></span> | <span data-ttu-id="d8cbb-408">範囲演算子</span><span class="sxs-lookup"><span data-stu-id="d8cbb-408">Range operator</span></span> | `Int`
 <span data-ttu-id="d8cbb-409">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-409">`?` `|`</span></span> | <span data-ttu-id="d8cbb-410">三項</span><span class="sxs-lookup"><span data-stu-id="d8cbb-410">Ternary</span></span> | <span data-ttu-id="d8cbb-411">条件付き</span><span class="sxs-lookup"><span data-stu-id="d8cbb-411">Conditional</span></span> | <span data-ttu-id="d8cbb-412">`Bool`左側にある</span><span class="sxs-lookup"><span data-stu-id="d8cbb-412">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="d8cbb-413">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="d8cbb-413">`w/` `<-`</span></span> | <span data-ttu-id="d8cbb-414">三項</span><span class="sxs-lookup"><span data-stu-id="d8cbb-414">Ternary</span></span> | <span data-ttu-id="d8cbb-415">コピーと更新</span><span class="sxs-lookup"><span data-stu-id="d8cbb-415">Copy-and-update</span></span> | <span data-ttu-id="d8cbb-416">「[コピーと更新の式」を](#copy-and-update-expressions)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-416">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="whats-next"></a><span data-ttu-id="d8cbb-417">次の課題</span><span class="sxs-lookup"><span data-stu-id="d8cbb-417">What's Next?</span></span>
<span data-ttu-id="d8cbb-418">Q # の式を操作できるようになったので、操作と関数を定義して呼び出す方法については、「 [q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8cbb-418">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
