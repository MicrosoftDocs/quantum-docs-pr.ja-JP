---
title: Q での制御フロー#
description: ループ、条件、その他
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326542"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="854a0-103">Q での制御フロー#</span><span class="sxs-lookup"><span data-stu-id="854a0-103">Control Flow in Q#</span></span>

<span data-ttu-id="854a0-104">演算または関数内では、最も一般的な命令型の共通言語と同様に、各ステートメントが順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="854a0-105">ただし、この制御フローは、次の3つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="854a0-106">`if`命令</span><span class="sxs-lookup"><span data-stu-id="854a0-106">`if` statements</span></span>
- <span data-ttu-id="854a0-107">`for`for</span><span class="sxs-lookup"><span data-stu-id="854a0-107">`for` loops</span></span>
- <span data-ttu-id="854a0-108">`repeat`-`until`for</span><span class="sxs-lookup"><span data-stu-id="854a0-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="854a0-109">後者については、[後](#repeat-until-success-loop)で説明します。</span><span class="sxs-lookup"><span data-stu-id="854a0-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="854a0-110">`if`ただし、および `for` 制御フローの構造は、従来のほとんどのプログラミング言語をよく理解しています。</span><span class="sxs-lookup"><span data-stu-id="854a0-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="854a0-111">重要な点として、 `for` ループおよびステートメントは、 `if` 特殊化が自動生成される操作でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="854a0-112">この場合、ループの adjoint は方向を反転させ、 `for` 各反復の adjoint を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="854a0-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="854a0-113">これは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="854a0-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="854a0-114">靴を decidedly ている間に、試してみて、お客様の socks を試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="854a0-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="854a0-115">の場合は、それ以外の場合は。それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="854a0-115">If, Else-if, Else</span></span>

<span data-ttu-id="854a0-116">ステートメントでは、 `if` 条件付き実行がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="854a0-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="854a0-117">キーワード、 `if` 始めかっこ `(` 、ブール式、右かっこ `)` 、およびステートメントブロック ( _then_ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="854a0-118">この後には、任意の数の else if 句を指定できます。これらは、それぞれキーワード、 `elif` 始めかっこ `(` 、ブール式、右かっこ `)` 、およびステートメントブロック ( _else if_ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="854a0-119">最後に、ステートメントは、キーワードとそれ `else` に続く別のステートメントブロック ( _else_ブロック) で構成される else 句を使用して終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="854a0-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="854a0-120">`if`条件が評価され、true の場合は then ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="854a0-121">条件が false の場合、最初の else if 条件が評価されます。true の場合は、それ以外の場合は if ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="854a0-122">それ以外の場合は、2番目の else-if ブロックがテストされ、3番目以降の場合は、true 条件を持つ句が検出されるか、それ以上の else if 句が存在しなくなるまで続きます。</span><span class="sxs-lookup"><span data-stu-id="854a0-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="854a0-123">元の if 条件とすべての else-if 句が false と評価された場合、else ブロックが指定されていると、else ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="854a0-124">実行されるブロックはいずれも、それ自体のスコープ内で実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="854a0-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="854a0-125">`if`、、またはブロック内で行われたバインディングは、末尾の後には表示され `elif` `else` ません。</span><span class="sxs-lookup"><span data-stu-id="854a0-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="854a0-126">たとえば、</span><span class="sxs-lookup"><span data-stu-id="854a0-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="854a0-127">または</span><span class="sxs-lookup"><span data-stu-id="854a0-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="854a0-128">For ループ</span><span class="sxs-lookup"><span data-stu-id="854a0-128">For Loop</span></span>

<span data-ttu-id="854a0-129">`for`ステートメントでは、整数範囲または配列に対する反復処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="854a0-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="854a0-130">ステートメントは、キーワード、 `for` 始めかっこ `(` 、その後に記号または記号の組、キーワード `in` 、型 `Range` または配列の式、右かっこ `)` 、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="854a0-131">ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="854a0-132">範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="854a0-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="854a0-133">式はループに入る前に完全に評価され、ループの実行中は変更されません。</span><span class="sxs-lookup"><span data-stu-id="854a0-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="854a0-134">ループ変数は、ループ本体の各入口でバインドされ、本文の最後にバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="854a0-135">特に、ループ変数は for ループの完了後にバインドされません。</span><span class="sxs-lookup"><span data-stu-id="854a0-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="854a0-136">宣言されたシンボルのバインドは不変であり、他の変数バインドと同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="854a0-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="854a0-137">例としては、 `qubits` qubits (型) のレジスタを使用する場合があります。 `Qubit[]`</span><span class="sxs-lookup"><span data-stu-id="854a0-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="854a0-138">最後に、算術-左2項演算子を使用しました。その詳細については、 `<<<` 「[数値式](xref:microsoft.quantum.guide.expressions#numeric-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="854a0-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="854a0-139">繰り返し-成功ループ</span><span class="sxs-lookup"><span data-stu-id="854a0-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="854a0-140">Q # 言語を使用すると、古典制御フローは qubits の測定結果に依存することになります。</span><span class="sxs-lookup"><span data-stu-id="854a0-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="854a0-141">この機能により、確率論的を実装するためのコンピューティングコストを削減できる強力なガジェットを実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="854a0-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="854a0-142">例として、Q # では、いわゆる*繰り返し-成功*(ru) のパターンを簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="854a0-143">これらの RU パターンは、基本ゲートの観点から*予想*低コストの確率論的プログラムですが、実際のコストは、考えられるさまざまな branchings の実際の実行と実際のインターリーブによって異なります。</span><span class="sxs-lookup"><span data-stu-id="854a0-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="854a0-144">Repeat To Success (RU) パターンを容易にするために、Q # はコンストラクトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="854a0-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="854a0-145">ここで `expression` 、は型の値に評価される有効な式です `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="854a0-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="854a0-146">ループの本体が実行され、条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="854a0-147">条件が true の場合、ステートメントは完了します。それ以外の場合は、fixup が実行され、ループ本体からステートメントが再実行されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="854a0-148">Repeat/until ループの3つの部分 (本文、テスト、および修正) は、*繰り返しごとに*1 つのスコープとして扱われるので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="854a0-149">ただし、修正の実行を完了すると、ステートメントのスコープが終了します。これにより、本体またはフィックスアップ中に作成されたシンボルバインドは、後続の繰り返しでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="854a0-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="854a0-150">さらに、 `fixup` 多くの場合、ステートメントは便利ですが、必ずしも必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="854a0-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="854a0-151">必要でない場合、コンストラクト</span><span class="sxs-lookup"><span data-stu-id="854a0-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="854a0-152">は、有効な RUS パターンでもあります。</span><span class="sxs-lookup"><span data-stu-id="854a0-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="854a0-153">このページの下部には、 [ru ループの例](#repeat-until-success-examples)がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="854a0-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="854a0-154">関数内での繰り返しの成功ループの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="854a0-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="854a0-155">対応する機能は、関数の while ループによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="854a0-156">While ループ</span><span class="sxs-lookup"><span data-stu-id="854a0-156">While Loop</span></span>

<span data-ttu-id="854a0-157">繰り返し-成功パターンには、クォンタム固有の connotation があります。</span><span class="sxs-lookup"><span data-stu-id="854a0-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="854a0-158">これらは、特定のクラスのクォンタムアルゴリズムで広く使用されているため、Q # の専用言語構成要素です。</span><span class="sxs-lookup"><span data-stu-id="854a0-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="854a0-159">ただし、条件に基づいて中断されるループでは、実行の長さがコンパイル時に不明であるため、クォンタムランタイムでは特に注意して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="854a0-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="854a0-160">一方、関数内での使用は、従来の (非クォンタム) ハードウェアで実行されるコードのみを含むため、問題はありません。</span><span class="sxs-lookup"><span data-stu-id="854a0-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="854a0-161">そのため、Q # では、関数内でのみ while ループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="854a0-162">ステートメントは、 `while` キーワード、 `while` 始めかっこ `(` 、条件 (つまり、ブール式)、終わりかっこ `)` 、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="854a0-163">ステートメントブロック (ループの本体) は、条件がに評価される限り実行され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="854a0-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="854a0-164">Return ステートメント</span><span class="sxs-lookup"><span data-stu-id="854a0-164">Return Statement</span></span>

<span data-ttu-id="854a0-165">Return ステートメントは、操作または関数の実行を終了し、呼び出し元に値を返します。</span><span class="sxs-lookup"><span data-stu-id="854a0-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="854a0-166">これは、キーワードと、 `return` 適切な型の式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="854a0-167">空のタプルを返す呼び出し可能なは、 `()` return ステートメントを必要としません。</span><span class="sxs-lookup"><span data-stu-id="854a0-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="854a0-168">早期終了が必要な場合は、 `return ()` この場合はを使用できます。</span><span class="sxs-lookup"><span data-stu-id="854a0-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="854a0-169">他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="854a0-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="854a0-170">操作内に return ステートメントの最大数がありません。</span><span class="sxs-lookup"><span data-stu-id="854a0-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="854a0-171">ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="854a0-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="854a0-172">たとえば、</span><span class="sxs-lookup"><span data-stu-id="854a0-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="854a0-173">or</span><span class="sxs-lookup"><span data-stu-id="854a0-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="854a0-174">or</span><span class="sxs-lookup"><span data-stu-id="854a0-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="854a0-175">Fail ステートメント</span><span class="sxs-lookup"><span data-stu-id="854a0-175">Fail Statement</span></span>

<span data-ttu-id="854a0-176">Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="854a0-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="854a0-177">これは、キーワードと、その `fail` 後に続く文字列と終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="854a0-178">文字列は、エラーメッセージとしてクラシックドライバーに返されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="854a0-179">操作内の fail ステートメントの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="854a0-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="854a0-180">ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="854a0-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="854a0-181">たとえば、</span><span class="sxs-lookup"><span data-stu-id="854a0-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="854a0-182">または、挿入[文字列](xref:microsoft.quantum.guide.expressions#interpolated-strings)を使用します。</span><span class="sxs-lookup"><span data-stu-id="854a0-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="854a0-183">繰り返し-成功の例</span><span class="sxs-lookup"><span data-stu-id="854a0-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="854a0-184">無理数軸に関する単一の qubit ローテーションの ru パターン</span><span class="sxs-lookup"><span data-stu-id="854a0-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="854a0-185">一般的なユースケースでは、次の Q # 操作は、Bloch 球の $ (I + 2i Z)/\ sqrt $ の無理数軸を中心とした回転を実装し {5} ます。</span><span class="sxs-lookup"><span data-stu-id="854a0-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="854a0-186">これは、既知の RUS パターンを使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="854a0-187">スコープ内の変更可能な変数を含む RU ループ</span><span class="sxs-lookup"><span data-stu-id="854a0-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="854a0-188">この例では、変更可能な変数を使用する方法を示します。この変数は、繰り返しの反復処理の `finished` ループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。</span><span class="sxs-lookup"><span data-stu-id="854a0-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="854a0-189">使用しない RU`fixup`</span><span class="sxs-lookup"><span data-stu-id="854a0-189">RUS without `fixup`</span></span>

<span data-ttu-id="854a0-190">たとえば、次のコードは、 {5} およびゲートを使用して、確率論的回線を実装する回線であり、重要な回転 $V ゲート (& 3)、(+ 2 i Z)/\ sqrt $ が実装されてい `H` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="854a0-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="854a0-191">ループは、平均で $-frac {8} {5} $ 繰り返しで終了します。</span><span class="sxs-lookup"><span data-stu-id="854a0-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="854a0-192">詳細については、「繰り返し-成功するまで」を参照してください。これは、[*シングル qubit 2014 Unitaries 非決定的に分解したもの*](https://arxiv.org/abs/1311.1074)です。</span><span class="sxs-lookup"><span data-stu-id="854a0-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="854a0-193">クォンタムの状態を準備する RU</span><span class="sxs-lookup"><span data-stu-id="854a0-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="854a0-194">最後に、"$ \ket{+} $" 状態から始まるクォンタムの状態を準備する RUS パターンの例を示します。この例では、$ \ frac {1} {\ sqrt {3} } \ left (\ sqrt {2} \ket {0} + \ket {1} \ 右) $ が使用されています。</span><span class="sxs-lookup"><span data-stu-id="854a0-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="854a0-195">[標準ライブラリで提供されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="854a0-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="854a0-196">この操作に示されている重要なプログラム機能は、ループのより複雑な部分です。これには、 `fixup` クォンタム操作が含まれます。また、ステートメントを使用して、 `AssertProb` プログラム内の特定の特定のポイントでクォンタムの状態を測定する確率を確認します。</span><span class="sxs-lookup"><span data-stu-id="854a0-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="854a0-197">および操作の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」も参照してください [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。</span><span class="sxs-lookup"><span data-stu-id="854a0-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="854a0-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="854a0-198">Next steps</span></span>

<span data-ttu-id="854a0-199">Q # での[テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging)について説明します。</span><span class="sxs-lookup"><span data-stu-id="854a0-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>