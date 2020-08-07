---
title: の式Q#
description: 定数、変数、演算子、操作、および関数をの式として指定、参照、および結合する方法について説明 Q# します。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869615"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="0b435-103">の式Q#</span><span class="sxs-lookup"><span data-stu-id="0b435-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="0b435-104">数値式</span><span class="sxs-lookup"><span data-stu-id="0b435-104">Numeric Expressions</span></span>

<span data-ttu-id="0b435-105">数値式は `Int` 、、 `BigInt` 、または型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="0b435-106">つまり、整数または浮動小数点数のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="0b435-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="0b435-107">`Int`のリテラル Q# は、一連の数字として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0b435-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="0b435-108">16進整数とバイナリ整数がサポートされ、それぞれとプレフィックスを使用して記述され `0x` `0b` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="0b435-109">`BigInt`のリテラルに Q# は、末尾 `l` またはサフィックスがあり `L` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="0b435-110">16進数の大きな整数がサポートされており、プレフィックス "0x" を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="0b435-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="0b435-111">したがって、リテラルの有効な使用法は次のとおりです `BigInt` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="0b435-112">`Double`のリテラル Q# は、10進数を使用して記述された浮動小数点数です。</span><span class="sxs-lookup"><span data-stu-id="0b435-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="0b435-113">小数点、 `.` 、または "e" または "e" で示された指数部を使用して記述することもできます (その後は、負の符号と小数点以下の桁数のみが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="0b435-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="0b435-114">有効なリテラルは、、 `Double` `0.0` `1.2e5` 、 `1e-5` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="0b435-115">任意の要素型の配列式が指定されている場合は、 `Int` 組み込み関数を使用して式を作成できます。その際、 [`Length`](xref:microsoft.quantum.core.length) かっこで囲まれた配列式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b435-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="0b435-116">たとえば、 `a` が配列にバインドされている場合、 `Length(a)` は整数式になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="0b435-117">`b`が整数の配列の配列である場合 `Int[][]` 、は `Length(b)` のサブ配列の数です `b` `Length(b[1])` 。はの2番目のサブ配列の整数の数です `b` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="0b435-118">同じ型の2つの数値式が指定されている場合、二項演算子 `+` 、 `-` 、、およびを使用して、 `*` `/` 新しい数値式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0b435-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="0b435-119">新しい式の型は、構成式の型と同じです。</span><span class="sxs-lookup"><span data-stu-id="0b435-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="0b435-120">2つの整数式を指定する場合は、二項演算子 `^` (power) を使用して新しい整数式を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b435-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="0b435-121">同様に、 `^` 2 つの double 式を使用して、新しい double 式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b435-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="0b435-122">最後に、を使用して、左に大きな整数を指定し、右側の整数を使用し `^` て新しい大きな整数式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0b435-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="0b435-123">この場合、2番目のパラメーターは32ビットにする必要があります。そうでない場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0b435-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="0b435-124">2つの整数または整数の式を指定した場合は、 `%` (剰余)、 `&&&` (ビットごとの and)、 `|||` (ビットごとの or)、または `^^^` (ビットごとの XOR) 演算子を使用して、新しい整数または整数式を形成します。</span><span class="sxs-lookup"><span data-stu-id="0b435-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="0b435-125">左に整数式または整数式を指定し、右側に整数式を指定する場合は、 `<<<` (算術左シフト) 演算子または `>>>` (算術右シフト) 演算子を使用して、左側の式と同じ型の新しい式を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b435-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="0b435-126">シフト演算の2番目のパラメーター (シフト量) は、0以上である必要があります。負のシフト量の動作は未定義です。</span><span class="sxs-lookup"><span data-stu-id="0b435-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="0b435-127">また、いずれかのシフト操作のシフト量は、32ビットにも適合する必要があります。そうでない場合は、ランタイムエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0b435-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="0b435-128">シフトされた数値が整数である場合は、シフトの量が解釈されます `mod 64` 。つまり、シフト1と65のシフトは同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="0b435-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="0b435-129">整数値と大きな整数値の両方に対して、シフトは算術演算です。</span><span class="sxs-lookup"><span data-stu-id="0b435-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="0b435-130">負の値を左または右にシフトすると、負の数値になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="0b435-131">つまり、1つのステップを左または右にシフトすることは、それぞれ2で乗算または除算することと同じです。</span><span class="sxs-lookup"><span data-stu-id="0b435-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="0b435-132">整数の除算と整数の剰余は、C# と同じ負の数値の動作に従います。</span><span class="sxs-lookup"><span data-stu-id="0b435-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="0b435-133">つまり、は `a % b` 常にと同じ符号を持ち、は常にと `a` `b * (a / b) + a % b` `a` なります。</span><span class="sxs-lookup"><span data-stu-id="0b435-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="0b435-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="0b435-135">5</span><span class="sxs-lookup"><span data-stu-id="0b435-135">5</span></span> | <span data-ttu-id="0b435-136">2</span><span class="sxs-lookup"><span data-stu-id="0b435-136">2</span></span> | <span data-ttu-id="0b435-137">2</span><span class="sxs-lookup"><span data-stu-id="0b435-137">2</span></span> | <span data-ttu-id="0b435-138">1</span><span class="sxs-lookup"><span data-stu-id="0b435-138">1</span></span>
 <span data-ttu-id="0b435-139">5</span><span class="sxs-lookup"><span data-stu-id="0b435-139">5</span></span> | <span data-ttu-id="0b435-140">-2</span><span class="sxs-lookup"><span data-stu-id="0b435-140">-2</span></span> | <span data-ttu-id="0b435-141">-2</span><span class="sxs-lookup"><span data-stu-id="0b435-141">-2</span></span> | <span data-ttu-id="0b435-142">1</span><span class="sxs-lookup"><span data-stu-id="0b435-142">1</span></span>
 <span data-ttu-id="0b435-143">-5</span><span class="sxs-lookup"><span data-stu-id="0b435-143">-5</span></span> | <span data-ttu-id="0b435-144">2</span><span class="sxs-lookup"><span data-stu-id="0b435-144">2</span></span> | <span data-ttu-id="0b435-145">-2</span><span class="sxs-lookup"><span data-stu-id="0b435-145">-2</span></span> | <span data-ttu-id="0b435-146">-1</span><span class="sxs-lookup"><span data-stu-id="0b435-146">-1</span></span>
 <span data-ttu-id="0b435-147">-5</span><span class="sxs-lookup"><span data-stu-id="0b435-147">-5</span></span> | <span data-ttu-id="0b435-148">-2</span><span class="sxs-lookup"><span data-stu-id="0b435-148">-2</span></span> | <span data-ttu-id="0b435-149">2</span><span class="sxs-lookup"><span data-stu-id="0b435-149">2</span></span> | <span data-ttu-id="0b435-150">-1</span><span class="sxs-lookup"><span data-stu-id="0b435-150">-1</span></span>

<span data-ttu-id="0b435-151">大規模な整数除算および剰余演算は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="0b435-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="0b435-152">任意の数値式を指定すると、単項演算子を使用して新しい式を作成でき `-` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="0b435-153">新しい式は、構成式と同じ型です。</span><span class="sxs-lookup"><span data-stu-id="0b435-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="0b435-154">整数または大きな整数式を指定する場合は、 `~~~` (ビットごとの補数) 単項演算子を使用して、同じ型の新しい式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0b435-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="0b435-155">Boolean 式</span><span class="sxs-lookup"><span data-stu-id="0b435-155">Boolean Expressions</span></span>

<span data-ttu-id="0b435-156">2つの `Bool` リテラル値は、 `true` と `false` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="0b435-157">同じプリミティブ型の2つの式がある場合、 `==` および `!=` 二項演算子を使用して式を作成でき `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="0b435-158">式は、2つの式が等しい場合は true、それ以外の場合は false です。</span><span class="sxs-lookup"><span data-stu-id="0b435-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="0b435-159">ユーザー定義型の値を比較することはできません。ラップ解除された値だけを比較できます。</span><span class="sxs-lookup"><span data-stu-id="0b435-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="0b435-160">たとえば、"ラップ解除" 演算子 `!` ([の Q# 型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)の詳細については、「」をご覧ください) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b435-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="0b435-161">値の等価比較 `Qubit` は、id の等価性を表します。つまり、2つの式が同じ qubit を識別するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="0b435-162">2つの qubits の状態は、この比較によって比較、アクセス、測定、または変更されません。</span><span class="sxs-lookup"><span data-stu-id="0b435-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="0b435-163">`Double`丸め効果が原因で、値の等価比較が誤解される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="0b435-164">たとえば、`49.0 * (1.0/49.0) != 1.0` のようにします。</span><span class="sxs-lookup"><span data-stu-id="0b435-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="0b435-165">2つの数値式を指定すると、二項演算子 `>` 、 `<` 、、およびを使用して、 `>=` `<=` 新しいブール式を作成できます。この式は、最初の式の値が、2番目の式の値よりも大きい、より小さい、より大きい、または等しい場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="0b435-166">2つのブール式を指定した場合は、二項演算子を使用して、 `and` 2 つの式の両方が true の場合に true となる新しいブール式を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b435-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="0b435-167">同様に、演算子を使用すると、 `or` 2 つの式のいずれかが true の場合に true となる式が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="0b435-168">任意のブール式を指定した `not` 場合、単項演算子を使用して新しいブール式を作成できます。これは、構成式が false の場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="0b435-169">文字列式</span><span class="sxs-lookup"><span data-stu-id="0b435-169">String expressions</span></span>

<span data-ttu-id="0b435-170">Q#`fail`ステートメント ([制御フロー](xref:microsoft.quantum.guide.controlflow#fail-statement)で説明されています) および標準関数で文字列を使用できるようにし [`Message`](xref:microsoft.quantum.intrinsic.message) ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="0b435-171">後者の特定の動作は、使用されるシミュレーターによって異なりますが、通常はプログラム中に呼び出されたときに、メッセージをホストコンソールに書き込み Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="0b435-172">内の文字列 Q# は、リテラルまたは挿入文字列です。</span><span class="sxs-lookup"><span data-stu-id="0b435-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="0b435-173">文字列リテラルは、ほとんどの言語の単純な文字列リテラルに似ています。これは、二重引用符で囲まれた Unicode 文字のシーケンス `" "` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="0b435-174">文字列の内部では、円記号を使用して `\` 二重引用符 () をエスケープしたり、改行 `\"` ( `\n` )、キャリッジリターン ( `\r` )、またはタブ () を挿入したりし `\t` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="0b435-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="0b435-176">挿入文字列</span><span class="sxs-lookup"><span data-stu-id="0b435-176">Interpolated strings</span></span>

<span data-ttu-id="0b435-177">Q#文字列補間の構文は、C# 構文のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="0b435-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="0b435-178">次に示すのは、関連する重要なポイント Q# です。</span><span class="sxs-lookup"><span data-stu-id="0b435-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="0b435-179">文字列リテラルを挿入文字列として識別するため、先頭に `$` の記号を追加してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="0b435-180">との間には、 `$` `"` 文字列リテラルを開始する空白文字を使用できません。</span><span class="sxs-lookup"><span data-stu-id="0b435-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="0b435-181">次に、関数を使用して、 [`Message`](xref:microsoft.quantum.intrinsic.message) 他の式と共に測定の結果をコンソールに書き込む基本的な例を示し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="0b435-182">有効な Q# 式は、挿入文字列に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0b435-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="0b435-183">挿入文字列内の式は Q# 、C# 構文ではなく構文に従います。</span><span class="sxs-lookup"><span data-stu-id="0b435-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="0b435-184">最も顕著な違いは、が Q# 逐語的 (複数行) の補間文字列をサポートしていないことです。</span><span class="sxs-lookup"><span data-stu-id="0b435-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="0b435-185">C# の構文の詳細については、「[*補間文字列*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="0b435-186">範囲の式</span><span class="sxs-lookup"><span data-stu-id="0b435-186">Range Expressions</span></span>

<span data-ttu-id="0b435-187">、、およびという3つの式が指定されている場合、式は、が `Int` `start` `step` `stop` `start .. step .. stop` 渡されるまで、最初の要素が `start` 、2番目の要素が、 `start+step` 3 番目の要素がである範囲式です `start+step+step` `stop` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="0b435-188">たとえば、が正の値やである場合、範囲は空になることがあり `step` `stop < start` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="0b435-189">範囲は両端を含みます。</span><span class="sxs-lookup"><span data-stu-id="0b435-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="0b435-190">つまり、との差 `start` `stop` がの整数の倍数である場合、 `step` 範囲の最後の要素はになり `stop` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="0b435-191">との2つの式が指定されて `Int` `start` `stop` いる場合、式はと `start .. stop` 等しい範囲式になり `start .. 1 .. stop` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="0b435-192">がより小さい場合でも、暗黙のは + 1 であることに注意して `step` `stop` `start` ください。この場合、範囲は空になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="0b435-193">範囲の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-193">Some example ranges are:</span></span>

- <span data-ttu-id="0b435-194">`1..3`の範囲は1、2、3です。</span><span class="sxs-lookup"><span data-stu-id="0b435-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="0b435-195">`2..2..5`は2、4の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="0b435-196">`2..2..6`は2、4、6の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="0b435-197">`6..-2..2`は6、4、2の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="0b435-198">`2..1`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="0b435-199">`2..6..7`は2の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="0b435-200">`2..2..1`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="0b435-201">`1..-1..2`は空の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0b435-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="0b435-202">Qubit 式</span><span class="sxs-lookup"><span data-stu-id="0b435-202">Qubit Expressions</span></span>

<span data-ttu-id="0b435-203">唯一の `Qubit` 式は、 `Qubit` 配列の値または配列要素にバインドされている記号です `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="0b435-204">リテラルがありません `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="0b435-205">P# li 式</span><span class="sxs-lookup"><span data-stu-id="0b435-205">Pauli Expressions</span></span>

<span data-ttu-id="0b435-206">、、、およびの4つの `Pauli` 値 `PauliI` は、 `PauliX` `PauliY` `PauliZ` すべて有効な `Pauli` 式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="0b435-207">それ以外の式は、 `Pauli` `Pauli` 配列の値または配列要素にバインドされるシンボルです `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="0b435-208">結果式</span><span class="sxs-lookup"><span data-stu-id="0b435-208">Result Expressions</span></span>

<span data-ttu-id="0b435-209">2つの `Result` 値 ( `One` と `Zero` ) は、有効な `Result` 式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="0b435-210">それ以外の式は、 `Result` `Result` 配列の値または配列要素にバインドされるシンボルです `Result` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="0b435-211">特に、 `One` は整数と同じではなく、 `1` これらの間に直接変換がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="0b435-212">とにも同じことが当てはまり `Zero` `0` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="0b435-213">タプル式</span><span class="sxs-lookup"><span data-stu-id="0b435-213">Tuple Expressions</span></span>

<span data-ttu-id="0b435-214">組リテラルは、適切な型の要素式のシーケンスで、かっこで囲まれたコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="0b435-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="0b435-215">たとえば、 `(1, One)` は `(Int, Result)` 式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="0b435-216">リテラル以外の唯一のタプル式は、タプル値にバインドされたシンボル、組配列の配列要素、およびタプルを返す呼び出し可能な呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="0b435-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="0b435-217">ユーザー定義型の式</span><span class="sxs-lookup"><span data-stu-id="0b435-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="0b435-218">ユーザー定義型のリテラルは、型名の後に型の基本タプル型のタプルリテラルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b435-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="0b435-219">たとえば、 `IntPair` がに基づくユーザー定義型である場合、 `(Int, Int)` `IntPair(2, 3)` はその型の有効なリテラルです。</span><span class="sxs-lookup"><span data-stu-id="0b435-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="0b435-220">リテラル以外に、ユーザー定義型の唯一の式は、その型の値、その型の配列の配列要素、およびその型を返す呼び出し可能な呼び出しの値にバインドされている記号です。</span><span class="sxs-lookup"><span data-stu-id="0b435-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="0b435-221">ラップ解除 (式の)</span><span class="sxs-lookup"><span data-stu-id="0b435-221">Unwrap Expressions</span></span>

<span data-ttu-id="0b435-222">で Q# は、ラップ解除演算子は末尾の感嘆符 `!` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="0b435-223">たとえば、 `IntPair` が基になる型のユーザー定義型で、 `(Int, Int)` `s` が値を持つ変数である場合、 `IntPair(2, 3)` はに `s!` `(2, 3)` なります。</span><span class="sxs-lookup"><span data-stu-id="0b435-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="0b435-224">他のユーザー定義型の観点から定義されたユーザー定義型の場合は、ラップ解除演算子を繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b435-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="0b435-225">たとえば、は、 `s!!` の二重ラップ解除された値を示し `s` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="0b435-226">したがって、 `WrappedPair` が基になる型のユーザー定義型で、 `IntPair` `t` が値を持つ変数である場合、 `WrappedPair(IntPair(1,2))` はに `t!!` `(1,2)` なります。</span><span class="sxs-lookup"><span data-stu-id="0b435-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="0b435-227">演算子は、 `!` 配列のインデックス作成およびスライス以外の他のすべての演算子よりも優先順位が高く `[]` なります。</span><span class="sxs-lookup"><span data-stu-id="0b435-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="0b435-228">`!`とを `[]` バインド位置。つまり、 `a[i]![3]` は `((a[i])!)[3]` `i` の th 要素を受け取り、 `a` ラップを解除してから、ラップ解除された値の3番目の要素 (配列である必要があります) を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b435-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="0b435-229">演算子の優先順位は、 `!` 明らかでない可能性がある1つの影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="0b435-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="0b435-230">関数または操作が、ラップされていない値を返す場合は、ラップ解除ではなく、引数のタプルが呼び出しにバインドされるように、関数または操作の呼び出しをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="0b435-231">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="0b435-232">配列式</span><span class="sxs-lookup"><span data-stu-id="0b435-232">Array Expressions</span></span>

<span data-ttu-id="0b435-233">配列リテラルは、角かっこで囲まれた、コンマで区切られた1つ以上の要素式のシーケンスです `[]` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="0b435-234">すべての要素は、同じ型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="0b435-235">同じ型の2つの配列を指定した場合、 `+` 2 つの配列を連結した新しい配列を作成するには、二項演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b435-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="0b435-236">たとえば、`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="0b435-237">配列の作成</span><span class="sxs-lookup"><span data-stu-id="0b435-237">Array Creation</span></span>

<span data-ttu-id="0b435-238">型と式を指定した場合は、演算子を使用して、 `Int` `new` 指定されたサイズの新しい配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b435-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="0b435-239">たとえば、では、 `new Int[i + 1]` `Int` 要素を含む新しい配列が割り当てら `i + 1` れます。</span><span class="sxs-lookup"><span data-stu-id="0b435-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="0b435-240">などの空の配列リテラル `[]` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0b435-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="0b435-241">代わりに、を使用して長さ0の配列を作成でき `new T[0]` ます。ここで、 `T` は適切な型のプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="0b435-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="0b435-242">新しい配列の要素は、型に依存する既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="0b435-243">ほとんどの場合、これはゼロのバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="0b435-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="0b435-244">エンティティへの参照である qubits と callables 指定できる場合、適切な既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="0b435-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="0b435-245">したがって、これらの型の場合、既定値は無効な参照です。これは、C# や Java などの言語での null 参照と同様に、ランタイムエラーを発生させずに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b435-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="0b435-246">要素を安全に使用するには、qubits または callables 含む配列を既定値以外の値で初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="0b435-247">適切な初期化ルーチンについては、「」を参照してください <xref:microsoft.quantum.arrays> 。</span><span class="sxs-lookup"><span data-stu-id="0b435-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="0b435-248">各型の既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0b435-248">The default values for each type are:</span></span>

<span data-ttu-id="0b435-249">Type</span><span class="sxs-lookup"><span data-stu-id="0b435-249">Type</span></span> | <span data-ttu-id="0b435-250">Default</span><span class="sxs-lookup"><span data-stu-id="0b435-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="0b435-251">_無効な qubit_</span><span class="sxs-lookup"><span data-stu-id="0b435-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="0b435-252">空の範囲。`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="0b435-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="0b435-253">_無効な呼び出し可能_</span><span class="sxs-lookup"><span data-stu-id="0b435-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="0b435-254">タプル型は要素ごとに初期化します。</span><span class="sxs-lookup"><span data-stu-id="0b435-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="0b435-255">配列要素</span><span class="sxs-lookup"><span data-stu-id="0b435-255">Array Elements</span></span>

<span data-ttu-id="0b435-256">配列式と式が指定され `Int` ている場合は、配列要素演算子を使用して新しい式を作成し `[]` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="0b435-257">新しい式は、配列の要素型と同じ型です。</span><span class="sxs-lookup"><span data-stu-id="0b435-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="0b435-258">たとえば、 `a` が型の配列にバインドされている場合、 `Double` `a[4]` は `Double` 式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="0b435-259">配列式が単純識別子でない場合は、要素を選択するためにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="0b435-260">たとえば、 `a` と `b` が両方とも型の配列である場合、 `Int` 連結の要素は次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="0b435-261">内のすべての配列 Q# は、0から始まります。</span><span class="sxs-lookup"><span data-stu-id="0b435-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="0b435-262">つまり、配列の最初の要素 `a` は常に `a[0]` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="0b435-263">配列スライス</span><span class="sxs-lookup"><span data-stu-id="0b435-263">Array Slices</span></span>

<span data-ttu-id="0b435-264">配列式と式を指定した `Range` 場合は、配列スライス演算子を使用して新しい式を作成し `[ ]` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="0b435-265">新しい式は配列と同じ型であり、で定義されている順序で、の要素によってインデックスが作成された配列項目を格納し `Range` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="0b435-266">たとえば、 `a` が型の配列にバインドされている場合、 `Double` `a[3..-1..0]` は、 `Double[]` の最初の4つの要素を含む式ですが、 `a` では逆の順序で表示され `a` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="0b435-267">が空の場合、結果とし `Range` て得られる配列スライスは長さが0になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="0b435-268">配列要素を参照する場合と同様に、配列式が単純識別子でない場合は、それをかっこで囲み、スライスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="0b435-269">たとえば、 `a` と `b` が両方とも型の配列である場合、 `Int` 連結のスライスは次のように表されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="0b435-270">推定される開始/終了値</span><span class="sxs-lookup"><span data-stu-id="0b435-270">Inferred start/end values</span></span>

<span data-ttu-id="0b435-271">[0.8 リリース](xref:microsoft.quantum.relnotes)以降では、範囲スライスのコンテキスト式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b435-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="0b435-272">特に、range スライシング式のコンテキストで範囲の開始値と終了値を省略できます。</span><span class="sxs-lookup"><span data-stu-id="0b435-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="0b435-273">その場合、コンパイラは次の規則を適用して、範囲の目的の区切り記号を推論します。</span><span class="sxs-lookup"><span data-stu-id="0b435-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="0b435-274">範囲の*開始*値を省略した場合、推論された開始値</span><span class="sxs-lookup"><span data-stu-id="0b435-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="0b435-275">ステップが指定されていない場合、または指定されたステップが正の場合、は0になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="0b435-276">指定された手順が負の場合に、スライスされた配列の長さから1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="0b435-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="0b435-277">範囲の*終了*値を省略した場合、推論された終了値</span><span class="sxs-lookup"><span data-stu-id="0b435-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="0b435-278">スライスされた配列の長さ、ステップが指定されていない場合、または指定されたステップが正の場合は1を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="0b435-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="0b435-279">指定されたステップが負の場合、は0になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="0b435-280">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b435-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="0b435-281">コピーと更新の式</span><span class="sxs-lookup"><span data-stu-id="0b435-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="0b435-282">すべての Q# 型は値型であるため (少し特別な役割を果たす qubits を使用)、値がシンボルにバインドされているとき、またはシンボルが再バインドされるときに "コピー" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="0b435-283">つまり、の動作 Q# は、代入演算子を使用してコピーが作成された場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="0b435-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="0b435-284">もちろん、実際には、関連する部分のみが必要に応じて再作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="0b435-285">これは、配列項目を更新できないため、配列のコピー方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="0b435-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="0b435-286">既存の配列を変更するには、*コピーと更新*のメカニズムを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="0b435-287">*コピーと更新*の式を使用して、既存の配列から新しい配列を作成することができます。この場合、との演算子を使用し `w/` `<-` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="0b435-288">コピーと更新の式は、という形式の式です。 `expression1 w/ expression2 <- expression3`</span><span class="sxs-lookup"><span data-stu-id="0b435-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="0b435-289">`expression1`何らかの型の型である必要があり `T[]` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="0b435-290">`expression2`で指定された、変更する配列内のインデックスを定義 `expression1` します。</span><span class="sxs-lookup"><span data-stu-id="0b435-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="0b435-291">`expression2`型または型のいずれかである必要があり `Int` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="0b435-292">`expression3`で `expression1` 指定されたインデックスに基づいて、の要素を更新するために使用される値です `expression2` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="0b435-293">`expression2`が型の場合 `Int` 、は `expression3` 型である必要があり `T` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="0b435-294">`expression2`が型の場合 `Range` 、は `expression3` 型である必要があり `T[]` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="0b435-295">たとえば、コピーと更新の式では、で指定された要素を `arr w/ idx <- value` 除き、すべての要素が内の対応する要素に設定された新しい配列を構築し `arr` ます。ただし、で指定した要素は、 `idx` の値に設定され `value` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="0b435-296">指定されたに `arr` 配列が含まれてい `[0,1,2,3]` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="0b435-297">`arr w/ 0 <- 10`は配列 `[10,1,2,3]` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="0b435-298">`arr w/ 2 <- 10`は配列 `[0,1,10,3]` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="0b435-299">`arr w/ 0..2..3 <- [10,12]`は配列 `[10,1,12,3]` です。</span><span class="sxs-lookup"><span data-stu-id="0b435-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="0b435-300">名前付き項目のコピーと更新の式</span><span class="sxs-lookup"><span data-stu-id="0b435-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="0b435-301">ユーザー定義型の名前付き項目についても、同様の式が存在します。</span><span class="sxs-lookup"><span data-stu-id="0b435-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="0b435-302">たとえば、型について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="0b435-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="0b435-303">`c`に型の値が含まれている場合 `Complex(1., -1.)` 、 `c w/ Re <- 0.` はに評価される型の式です `Complex` `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="0b435-304">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="0b435-304">Jagged Arrays</span></span>

<span data-ttu-id="0b435-305">ジャグ配列は、"配列の配列" と呼ばれることもあり、要素が配列である配列です。</span><span class="sxs-lookup"><span data-stu-id="0b435-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="0b435-306">ジャグ配列の要素のサイズは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="0b435-307">次の例は、乗算テーブルを表すジャグ配列を宣言および初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b435-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="0b435-308">呼び出し許容の配列</span><span class="sxs-lookup"><span data-stu-id="0b435-308">Arrays of callables</span></span> 

<span data-ttu-id="0b435-309">また、呼び出し可能な配列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b435-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="0b435-310">共通の要素型が演算型または関数型である場合、すべての要素の入力と出力の型が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="0b435-311">配列の要素型は、すべての要素でサポートされ[ているすべての機能をサポート](xref:microsoft.quantum.guide.operationsfunctions)しています。</span><span class="sxs-lookup"><span data-stu-id="0b435-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="0b435-312">たとえば、 `Op1` 、 `Op2` 、およびは `Op3` すべて操作です `Qubit[] => Unit` が、 `Op1` サポート、 `Adjoint` サポート `Op2` `Controlled` 、およびサポートの `Op3` 両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0b435-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="0b435-313">`[Op1, Op2]`は操作の配列です `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="0b435-314">`[Op1, Op3]`は操作の配列です `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="0b435-315">`[Op2, Op3]`は操作の配列です `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="0b435-316">ただし、操作 `(Qubit[] => Unit is Adj)` と `(Qubit[] => Unit is Ctl)` の共通基本型がであるのに対し、 `(Qubit[] => Unit)` これらの操作の*配列*は共通の基本型を共有しません。</span><span class="sxs-lookup"><span data-stu-id="0b435-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="0b435-317">たとえば、では、 `[[Op1], [Op2]]` 互換性のない2つの配列型との配列を作成しようとするため、現在、ではエラーが発生し `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="0b435-318">呼び出し可能の詳細については、このページの「呼び出し可能な[式](#callable-expressions)」または「 [」の Q# 操作と関数](xref:microsoft.quantum.guide.operationsfunctions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="0b435-319">条件式</span><span class="sxs-lookup"><span data-stu-id="0b435-319">Conditional Expressions</span></span>

<span data-ttu-id="0b435-320">同じ型の2つの式とブール式を指定した場合は、疑問符、、および縦棒を使用して条件式を形成し `?` `|` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="0b435-321">指定した `a==b ? c | d` 場合、条件式の値は、が true で、false である場合はになり `c` `a==b` `d` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="0b435-322">呼び出しが許容される条件式</span><span class="sxs-lookup"><span data-stu-id="0b435-322">Conditional expressions with callables</span></span>

<span data-ttu-id="0b435-323">条件式は、入力と出力が同じで、異なる機能をサポートする操作に評価される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="0b435-324">この場合、条件式の型は、両方の式でサポートされているすべての機能をサポートする入力と出力を持つ操作です。</span><span class="sxs-lookup"><span data-stu-id="0b435-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="0b435-325">たとえば、、 `Op1` `Op2` 、およびはすべてですが、はをサポートし、サポートし、 `Op3` `Qubit[]=>Unit` 両方を `Op1` `Adjoint` `Op2` `Controlled` `Op3` サポートします。</span><span class="sxs-lookup"><span data-stu-id="0b435-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="0b435-326">`flag ? Op1 | Op2`は `(Qubit[] => Unit)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="0b435-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="0b435-327">`flag ? Op1 | Op3`は `(Qubit[] => Unit is Adj)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="0b435-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="0b435-328">`flag ? Op2 | Op3`は `(Qubit[] => Unit is Ctl)` 操作です。</span><span class="sxs-lookup"><span data-stu-id="0b435-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="0b435-329">2つの結果式のいずれかに関数呼び出しまたは演算呼び出しが含まれている場合、その呼び出しは、その結果が呼び出しの値である場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="0b435-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="0b435-330">たとえば、 `a==b ? C(qs) | D(qs)` が true の場合、 `a==b` `C` 操作が呼び出されます。 false の場合は、操作だけが `D` 呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0b435-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="0b435-331">この方法は、他の言語の*ショートサーキット*に似ています。</span><span class="sxs-lookup"><span data-stu-id="0b435-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="0b435-332">呼び出し可能式</span><span class="sxs-lookup"><span data-stu-id="0b435-332">Callable Expressions</span></span>

<span data-ttu-id="0b435-333">呼び出し可能なリテラルは、コンパイルスコープで定義されている操作または関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="0b435-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="0b435-334">たとえば、 `X` は、標準ライブラリの操作を参照する操作リテラルであり、 `X` `Message` は標準ライブラリ関数を参照する関数リテラルです `Message` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="0b435-335">操作が `Adjoint` ファンクタをサポートする場合、 `Adjoint op` は演算式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="0b435-336">同様に、操作がファンクタをサポートする場合、 `Controlled` `Controlled op` は演算式です。</span><span class="sxs-lookup"><span data-stu-id="0b435-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="0b435-337">これらの式の型の詳細については、「[操作の特殊化の呼び出し](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="0b435-338">( `Adjoint` および `Controlled` ) は、ラップ解除演算子と配列のインデックス作成を除き、他のすべての演算子よりも密接にバインドさ `!` `[ ]` れます。</span><span class="sxs-lookup"><span data-stu-id="0b435-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="0b435-339">このため、操作で使用されている機能がサポートされていれば、次のすべてが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="0b435-340">型パラメーター化可能な呼び出し可能式</span><span class="sxs-lookup"><span data-stu-id="0b435-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="0b435-341">呼び出し可能なリテラルを値として使用することができます。たとえば、変数に代入したり、別の呼び出し可能なリテラルに渡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b435-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="0b435-342">この場合、呼び出し可能に[型パラメーター](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)がある場合は、呼び出し可能な値の一部としてパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="0b435-343">呼び出し可能な値には、指定されていない型パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b435-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="0b435-344">たとえば、 `Fun` がシグネチャを持つ関数の場合は、次のようになり `'T1->Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="0b435-345">呼び出し可能呼び出し式</span><span class="sxs-lookup"><span data-stu-id="0b435-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="0b435-346">呼び出し可能な式 (操作または関数) と、呼び出し可能なシグネチャの入力型の組式が指定されている場合は、呼び出し式にタプル式を追加することにより、*呼び出し式*を形成できます。</span><span class="sxs-lookup"><span data-stu-id="0b435-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="0b435-347">呼び出し式の型は、呼び出し可能なシグネチャの出力型です。</span><span class="sxs-lookup"><span data-stu-id="0b435-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="0b435-348">たとえば、 `Op` がシグネチャを持つ操作である場合 `((Int, Qubit) => Double)` 、 `Op(3, qubit1)` は型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="0b435-349">同様に、 `Sin` がシグネチャを持つ関数の場合 `(Double -> Double)` 、 `Sin(0.1)` は型の式です `Double` 。</span><span class="sxs-lookup"><span data-stu-id="0b435-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="0b435-350">最後に、 `Builder` がシグネチャを持つ関数の場合、 `(Int -> (Int -> Int))` `Builder(3)` はからへの関数になり `Int` `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="0b435-351">呼び出し可能な値の式の結果を呼び出すには、呼び出し可能な式を囲むかっこのペアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b435-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="0b435-352">したがって、前の段落からを呼び出した結果を呼び出すに `Builder` は、正しい構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b435-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="0b435-353">[型パラメーター付き](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)呼び出し可能呼び出しを呼び出す場合、呼び出し可能な式の後に、山かっこ内に実際の型パラメーターを指定でき `< >` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="0b435-354">通常、このアクションは、 Q# コンパイラが実際の型を推論するときには不要です。</span><span class="sxs-lookup"><span data-stu-id="0b435-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="0b435-355">ただし、型パラメーターの引数が指定されていない*場合は、* [部分的なアプリケーション](xref:microsoft.quantum.guide.operationsfunctions#partial-application)で必要になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="0b435-356">また、異なるファンのサポートを持つ操作を呼び出し可能に渡す場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="0b435-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="0b435-357">たとえば、がシグネチャを持ち、シグネチャを持ち、シグネチャを持つ場合、2番目の引数としてを呼び出し、3番目の引数としてを `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` 呼び出し `Func` `Op1` `Op2` `Op3` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="0b435-358">との型が異なるため、型指定が必要です。そのため、 `Op3` `Op1` コンパイラはこれを仕様なしにあいまいとして扱います。</span><span class="sxs-lookup"><span data-stu-id="0b435-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="0b435-359">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="0b435-359">Operator Precedence</span></span>

* <span data-ttu-id="0b435-360">すべての二項演算子は、を除き、右から結合され `^` ます。</span><span class="sxs-lookup"><span data-stu-id="0b435-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="0b435-361">`[ ]`配列のスライスおよびインデックス作成のための角かっこは、任意の演算子の前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="0b435-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="0b435-362">`Adjoint` `Controlled` 配列のインデックス作成後、他のすべての演算子の前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="0b435-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="0b435-363">演算と関数呼び出しのかっこは、演算子の前、配列のインデックス作成および関数の後にもバインドされます。</span><span class="sxs-lookup"><span data-stu-id="0b435-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="0b435-364">Q#演算子は優先順位の高い順になります。</span><span class="sxs-lookup"><span data-stu-id="0b435-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="0b435-365">演算子</span><span class="sxs-lookup"><span data-stu-id="0b435-365">Operator</span></span> | <span data-ttu-id="0b435-366">アリ</span><span class="sxs-lookup"><span data-stu-id="0b435-366">Arity</span></span> | <span data-ttu-id="0b435-367">説明</span><span class="sxs-lookup"><span data-stu-id="0b435-367">Description</span></span> | <span data-ttu-id="0b435-368">オペランドの型</span><span class="sxs-lookup"><span data-stu-id="0b435-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="0b435-369">末尾`!`</span><span class="sxs-lookup"><span data-stu-id="0b435-369">trailing `!`</span></span> | <span data-ttu-id="0b435-370">単項</span><span class="sxs-lookup"><span data-stu-id="0b435-370">Unary</span></span> | <span data-ttu-id="0b435-371">ラップ解除</span><span class="sxs-lookup"><span data-stu-id="0b435-371">Unwrap</span></span> | <span data-ttu-id="0b435-372">任意のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0b435-372">Any user-defined type</span></span>
 <span data-ttu-id="0b435-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="0b435-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="0b435-374">単項</span><span class="sxs-lookup"><span data-stu-id="0b435-374">Unary</span></span> | <span data-ttu-id="0b435-375">負の数値、ビットごとの補数、論理否定</span><span class="sxs-lookup"><span data-stu-id="0b435-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="0b435-376">`Int`、、 `BigInt` またはの場合 `Double` `-` `Int` は `BigInt` `~~~` `Bool` 、の場合は。`not`</span><span class="sxs-lookup"><span data-stu-id="0b435-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="0b435-377">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-377">Binary</span></span> | <span data-ttu-id="0b435-378">整数の累乗</span><span class="sxs-lookup"><span data-stu-id="0b435-378">Integer power</span></span> | <span data-ttu-id="0b435-379">`Int`底の場合は `BigInt` 、 `Int` 指数部の場合は</span><span class="sxs-lookup"><span data-stu-id="0b435-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="0b435-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="0b435-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="0b435-381">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-381">Binary</span></span> | <span data-ttu-id="0b435-382">除算、乗算、整数剰余</span><span class="sxs-lookup"><span data-stu-id="0b435-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="0b435-383">`Int`、、、、 `BigInt` `Double` `/` `*` `Int` または `BigInt` の場合は。`%`</span><span class="sxs-lookup"><span data-stu-id="0b435-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="0b435-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="0b435-384">`+`, `-`</span></span> | <span data-ttu-id="0b435-385">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-385">Binary</span></span> | <span data-ttu-id="0b435-386">加算または文字列と配列の連結、減算</span><span class="sxs-lookup"><span data-stu-id="0b435-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="0b435-387">`Int`、、 `BigInt` また `Double` は、また `String` はのいずれかの配列型`+`</span><span class="sxs-lookup"><span data-stu-id="0b435-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="0b435-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="0b435-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="0b435-389">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-389">Binary</span></span> | <span data-ttu-id="0b435-390">左シフト、右シフト</span><span class="sxs-lookup"><span data-stu-id="0b435-390">Left shift, right shift</span></span> | <span data-ttu-id="0b435-391">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0b435-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="0b435-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="0b435-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="0b435-393">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-393">Binary</span></span> | <span data-ttu-id="0b435-394">より小さい、より小さい、または等しい、より大きい、より大きい、または等しい比較</span><span class="sxs-lookup"><span data-stu-id="0b435-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="0b435-395">`Int`、、 `BigInt` または`Double`</span><span class="sxs-lookup"><span data-stu-id="0b435-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="0b435-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="0b435-396">`==`, `!=`</span></span> | <span data-ttu-id="0b435-397">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-397">Binary</span></span> | <span data-ttu-id="0b435-398">等しい、等しくない比較</span><span class="sxs-lookup"><span data-stu-id="0b435-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="0b435-399">任意のプリミティブ型</span><span class="sxs-lookup"><span data-stu-id="0b435-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="0b435-400">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-400">Binary</span></span> | <span data-ttu-id="0b435-401">ビット演算子 AND</span><span class="sxs-lookup"><span data-stu-id="0b435-401">Bitwise AND</span></span> | <span data-ttu-id="0b435-402">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0b435-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="0b435-403">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-403">Binary</span></span> | <span data-ttu-id="0b435-404">ビットごとの XOR</span><span class="sxs-lookup"><span data-stu-id="0b435-404">Bitwise XOR</span></span> | <span data-ttu-id="0b435-405">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0b435-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="0b435-406">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-406">Binary</span></span> | <span data-ttu-id="0b435-407">ビットごとの OR</span><span class="sxs-lookup"><span data-stu-id="0b435-407">Bitwise OR</span></span> | <span data-ttu-id="0b435-408">`Int` または `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0b435-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="0b435-409">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-409">Binary</span></span> | <span data-ttu-id="0b435-410">論理積</span><span class="sxs-lookup"><span data-stu-id="0b435-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="0b435-411">Binary</span><span class="sxs-lookup"><span data-stu-id="0b435-411">Binary</span></span> | <span data-ttu-id="0b435-412">論理和</span><span class="sxs-lookup"><span data-stu-id="0b435-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="0b435-413">Binary/三項</span><span class="sxs-lookup"><span data-stu-id="0b435-413">Binary/Ternary</span></span> | <span data-ttu-id="0b435-414">範囲演算子</span><span class="sxs-lookup"><span data-stu-id="0b435-414">Range operator</span></span> | `Int`
 <span data-ttu-id="0b435-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="0b435-415">`?` `|`</span></span> | <span data-ttu-id="0b435-416">三項</span><span class="sxs-lookup"><span data-stu-id="0b435-416">Ternary</span></span> | <span data-ttu-id="0b435-417">条件付き</span><span class="sxs-lookup"><span data-stu-id="0b435-417">Conditional</span></span> | <span data-ttu-id="0b435-418">`Bool`左側にある</span><span class="sxs-lookup"><span data-stu-id="0b435-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="0b435-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="0b435-419">`w/` `<-`</span></span> | <span data-ttu-id="0b435-420">三項</span><span class="sxs-lookup"><span data-stu-id="0b435-420">Ternary</span></span> | <span data-ttu-id="0b435-421">コピーと更新</span><span class="sxs-lookup"><span data-stu-id="0b435-421">Copy-and-update</span></span> | <span data-ttu-id="0b435-422">「[コピーと更新の式」を](#copy-and-update-expressions)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b435-423">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0b435-423">Next steps</span></span>

<span data-ttu-id="0b435-424">で式を操作できるようになったので、操作と関数 Q# を[ Q# ](xref:microsoft.quantum.guide.operationsfunctions)定義して呼び出す方法については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b435-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
