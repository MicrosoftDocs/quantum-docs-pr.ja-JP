---
title: 制御フロー Q#
description: ループ、条件、その他
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833514"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="3346f-103">制御フロー Q#</span><span class="sxs-lookup"><span data-stu-id="3346f-103">Control flow in Q#</span></span>

<span data-ttu-id="3346f-104">演算または関数内では、各ステートメントが順序どおりに実行されます。これは、その他の一般的な従来の言語と似ています。</span><span class="sxs-lookup"><span data-stu-id="3346f-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="3346f-105">ただし、制御フローを変更するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3346f-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="3346f-106">`if` ステートメント</span><span class="sxs-lookup"><span data-stu-id="3346f-106">`if` statements</span></span>
* <span data-ttu-id="3346f-107">`for` for</span><span class="sxs-lookup"><span data-stu-id="3346f-107">`for` loops</span></span>
* <span data-ttu-id="3346f-108">`repeat-until-success` for</span><span class="sxs-lookup"><span data-stu-id="3346f-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="3346f-109">活用 ( `apply-within` ステートメント)</span><span class="sxs-lookup"><span data-stu-id="3346f-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="3346f-110">`if`および `for` 制御フローの構造は、ほとんどの一般的なプログラミング言語に慣れています。</span><span class="sxs-lookup"><span data-stu-id="3346f-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="3346f-111">[`Repeat-until-success`](#repeat-until-success-loop) ループと [活用](#conjugations) については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="3346f-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="3346f-112">重要な点として、 `for` ループおよびステートメントは、 `if` [特殊化](xref:microsoft.quantum.guide.operationsfunctions) が自動生成される操作で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3346f-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="3346f-113">このシナリオでは、ループの adjoint が方向を反転させ、 `for` 各反復の adjoint を取得します。</span><span class="sxs-lookup"><span data-stu-id="3346f-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="3346f-114">このアクションは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3346f-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="3346f-115">の場合は、それ以外の場合は。それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="3346f-115">If, Else-if, Else</span></span>

<span data-ttu-id="3346f-116">ステートメントでは、 `if` 条件付き処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3346f-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="3346f-117">キーワード、 `if` かっこで囲まれたブール式、およびステートメントブロック ( _then_ ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="3346f-118">必要に応じて、任意の数の else 句を使用できます。各句は、キーワード、 `elif` かっこで囲まれたブール式、およびステートメントブロック ( _else_ ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="3346f-119">最後に、ステートメントは、キーワードとそれ `else` に続く別のステートメントブロック ( _else_ ブロック) で構成される else 句を使用して終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="3346f-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="3346f-120">`if`条件が評価され、 *true*の場合は*then*ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-120">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="3346f-121">条件が *false*の場合、最初の else if 条件が評価されます。true の場合は、 *else if* ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-121">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="3346f-122">それ以外の場合は、2番目の else-if ブロックが評価され、次に3番目のは、true 条件を持つ句が検出されるか、それ以上 else if 句が存在しなくなるまで続きます。</span><span class="sxs-lookup"><span data-stu-id="3346f-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="3346f-123">元の *if* 条件とすべての else-if 句が *false*と評価された場合、 *else* ブロックが実行されます (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3346f-123">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="3346f-124">いずれかのブロックが実行されると、それ自体のスコープ内で実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3346f-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="3346f-125">`if`、 `elif` 、またはブロック内で行われたバインディングは、ブロックの終了後には `else` 参照できません。</span><span class="sxs-lookup"><span data-stu-id="3346f-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="3346f-126">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3346f-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="3346f-127">or</span><span class="sxs-lookup"><span data-stu-id="3346f-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="3346f-128">For ループ</span><span class="sxs-lookup"><span data-stu-id="3346f-128">For loop</span></span>

<span data-ttu-id="3346f-129">`for`ステートメントでは、整数範囲または配列に対する反復処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3346f-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="3346f-130">ステートメントは、キーワードと、 `for` その後にシンボルまたは記号の組、キーワード、 `in` 型 `Range` または配列の式、すべてのかっこ内、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="3346f-131">ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="3346f-132">範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3346f-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="3346f-133">式はループに入る前に完全に評価され、ループの実行中は変更されません。</span><span class="sxs-lookup"><span data-stu-id="3346f-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="3346f-134">ループ変数は、ループ本体への各入り口でバインドされ、本文の末尾でバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="3346f-135">ループ変数は、for ループの完了後にバインドされません。</span><span class="sxs-lookup"><span data-stu-id="3346f-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="3346f-136">ループ変数のバインドは不変であり、他の変数バインドと同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="3346f-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="3346f-137">これらの例で `qubits` は、は qubits (型) のレジスタです。 `Qubit[]`</span><span class="sxs-lookup"><span data-stu-id="3346f-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="3346f-138">最後に、算術シフト左の二項演算子のを使用して `<<<` います。</span><span class="sxs-lookup"><span data-stu-id="3346f-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="3346f-139">詳細については、「 [数値式](xref:microsoft.quantum.guide.expressions#numeric-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3346f-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="3346f-140">繰り返し-成功ループ</span><span class="sxs-lookup"><span data-stu-id="3346f-140">Repeat-until-success loop</span></span>

<span data-ttu-id="3346f-141">この言語では、 Q# 古典制御フローは qubits の測定結果に依存します。</span><span class="sxs-lookup"><span data-stu-id="3346f-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="3346f-142">さらに、この機能により、unitaries を実装するための計算コストを削減できる強力なガジェットを実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3346f-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="3346f-143">この例として、の *繰り返しの成功* (ru) パターンが挙げられ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="3346f-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="3346f-144">これらの RU パターンは、基本的なゲートの観点から、 *予想* 低コストの確率論的プログラムです。発生したコストは、実際の実行と、考えられる複数の branchings のインターリーブによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3346f-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="3346f-145">繰り返し-成功 (RU) パターンを容易にするために、は Q# コンストラクトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3346f-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="3346f-146">ここで `expression` 、は型の値に評価される有効な式です `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="3346f-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="3346f-147">ループの本体が実行され、条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="3346f-148">条件が true の場合、ステートメントは完了します。それ以外の場合は、フィックスアップが実行され、ステートメントがループ本体から開始され、再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="3346f-149">RUS ループの3つの部分 (本文、テスト、および修正) は、 *繰り返しごとに*1 つのスコープとして扱われるので、本文にバインドされているシンボルはテストと修正の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3346f-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="3346f-150">ただし、修正の実行を完了すると、ステートメントのスコープが終了します。これにより、本体またはフィックスアップ中に作成されたシンボルバインドは、後続の繰り返しでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3346f-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="3346f-151">さらに、 `fixup` 多くの場合、ステートメントは便利ですが、必ずしも必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="3346f-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="3346f-152">必要でない場合、コンストラクト</span><span class="sxs-lookup"><span data-stu-id="3346f-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="3346f-153">は、有効な RUS パターンでもあります。</span><span class="sxs-lookup"><span data-stu-id="3346f-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="3346f-154">その他の例と詳細については、この記事の「 [繰り返し-成功の例](#repeat-until-success-examples) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3346f-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="3346f-155">関数内での繰り返しの成功ループの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="3346f-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="3346f-156">*While*ループを使用して、関数内で対応する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3346f-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="3346f-157">while ループ</span><span class="sxs-lookup"><span data-stu-id="3346f-157">While loop</span></span>

<span data-ttu-id="3346f-158">繰り返し-成功パターンには、クォンタム固有の connotation があります。</span><span class="sxs-lookup"><span data-stu-id="3346f-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="3346f-159">これらは、クォンタムアルゴリズムの特定のクラスで広く使用されているため、の専用言語構成要素 Q# です。</span><span class="sxs-lookup"><span data-stu-id="3346f-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="3346f-160">ただし、条件に基づいて中断されるループは、実行の長さがコンパイル時に不明であるため、クォンタムのランタイムでは特に注意して処理されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="3346f-161">ただし、これらのループには従来の (非クォンタム) ハードウェアで実行されるコードのみが含まれているため、関数内での使用は問題ありません。</span><span class="sxs-lookup"><span data-stu-id="3346f-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="3346f-162">Q#したがって、では、関数内でのみ while ループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3346f-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="3346f-163">ステートメントは、 `while` キーワード、 `while` かっこで囲まれたブール式、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="3346f-164">ステートメントブロック (ループの本体) は、条件がと評価されている限り実行され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="3346f-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="3346f-165">活用</span><span class="sxs-lookup"><span data-stu-id="3346f-165">Conjugations</span></span>

<span data-ttu-id="3346f-166">従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。</span><span class="sxs-lookup"><span data-stu-id="3346f-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="3346f-167">これらの効果は、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。</span><span class="sxs-lookup"><span data-stu-id="3346f-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="3346f-168">クォンタムコンピューティングの一般的なパターンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3346f-168">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="3346f-169">Q# では、前の変換を実装する活用形ステートメントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3346f-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="3346f-170">このステートメントを使用すると、 `ApplyWith` 次のように操作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="3346f-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="3346f-171">このような活用形ステートメントは、外部および内部の変換を操作として簡単に使用できない場合に便利ですが、複数のステートメントで構成されるブロックで記述する方が便利です。</span><span class="sxs-lookup"><span data-stu-id="3346f-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="3346f-172">内部ブロックで定義されているステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="3346f-173">内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="3346f-174">Return ステートメント</span><span class="sxs-lookup"><span data-stu-id="3346f-174">Return Statement</span></span>

<span data-ttu-id="3346f-175">Return ステートメントは、操作または関数の実行を終了し、値を呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="3346f-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="3346f-176">これは、キーワードと、 `return` 適切な型の式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="3346f-177">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3346f-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="3346f-178">or</span><span class="sxs-lookup"><span data-stu-id="3346f-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="3346f-179">空のタプルを返す呼び出し可能なは、 `()` return ステートメントを必要としません。</span><span class="sxs-lookup"><span data-stu-id="3346f-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="3346f-180">操作または関数からの早期終了を指定するには、を使用し `return ();` ます。</span><span class="sxs-lookup"><span data-stu-id="3346f-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="3346f-181">他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3346f-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="3346f-182">操作内に return ステートメントの最大数がありません。</span><span class="sxs-lookup"><span data-stu-id="3346f-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="3346f-183">ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="3346f-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="3346f-184">Fail ステートメント</span><span class="sxs-lookup"><span data-stu-id="3346f-184">Fail statement</span></span>

<span data-ttu-id="3346f-185">Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="3346f-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="3346f-186">これは、キーワードと、その `fail` 後に続く文字列と終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="3346f-187">このステートメントは、文字列をエラーメッセージとしてクラシックドライバーに返します。</span><span class="sxs-lookup"><span data-stu-id="3346f-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="3346f-188">操作内の fail ステートメントの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3346f-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="3346f-189">ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="3346f-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="3346f-190">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3346f-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="3346f-191">または、挿入 [文字列](xref:microsoft.quantum.guide.expressions#interpolated-strings)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3346f-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="3346f-192">繰り返し-成功の例</span><span class="sxs-lookup"><span data-stu-id="3346f-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="3346f-193">無理数軸についてのシングル qubit ローテーションの ru パターン</span><span class="sxs-lookup"><span data-stu-id="3346f-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="3346f-194">一般的なユースケースでは、次の操作によって、 Q# Bloch 球の $ (I + 2i Z)/\ sqrt $ の無理数軸の周りの回転が実装され {5} ます。</span><span class="sxs-lookup"><span data-stu-id="3346f-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="3346f-195">実装では、既知の RUS パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3346f-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="3346f-196">スコープ内の変更可能な変数を使用した RU ループ</span><span class="sxs-lookup"><span data-stu-id="3346f-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="3346f-197">この例では、変更可能な変数を使用する方法を示します。この変数は、反復可能な反復処理の `finished` ループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。</span><span class="sxs-lookup"><span data-stu-id="3346f-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="3346f-198">使用しない RU `fixup`</span><span class="sxs-lookup"><span data-stu-id="3346f-198">RUS without `fixup`</span></span>

<span data-ttu-id="3346f-199">この例では、修正手順のない RUS ループを示します。</span><span class="sxs-lookup"><span data-stu-id="3346f-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="3346f-200">このコードは、 {5} およびゲートを使用して、確率論的回線で重要な回転ゲート $V (& a) = (\ bold 終了 + 2 i Z)/\ sqrt $ を実装し `H` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="3346f-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="3346f-201">ループは、平均で $-frac {8} {5} $ 繰り返しで終了します。</span><span class="sxs-lookup"><span data-stu-id="3346f-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="3346f-202">詳細については、「繰り返し-成功するまで」を参照してください。これは、 [*シングル qubit 2014 Unitaries 非決定的に分解したもの*](https://arxiv.org/abs/1311.1074) です。</span><span class="sxs-lookup"><span data-stu-id="3346f-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="3346f-203">クォンタムの状態を準備する RU</span><span class="sxs-lookup"><span data-stu-id="3346f-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="3346f-204">最後に、"$ \ket{+} $" 状態から始まるクォンタムの状態を準備する RUS パターンの例を次に示します。この例では、"$ \ frac {1} {\ sqrt {3} } \ left (\ sqrt {2} \ket {0} + \ket {1} \ right) $" となります。</span><span class="sxs-lookup"><span data-stu-id="3346f-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="3346f-205">この操作に示されている重要なプログラム機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3346f-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="3346f-206">ループのより複雑な `fixup` 部分。これには、クォンタム操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3346f-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="3346f-207">ステートメントを使用して、 `AssertMeasurementProbability` プログラム内の指定した特定のポイントでクォンタムの状態を測定する確率を確認します。</span><span class="sxs-lookup"><span data-stu-id="3346f-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="3346f-208">操作と操作の詳細につい [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ては、「 [テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3346f-208">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="3346f-209">詳細については、次を参照してください。 [標準ライブラリに用意されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)です。</span><span class="sxs-lookup"><span data-stu-id="3346f-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="3346f-210">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3346f-210">Next steps</span></span>

<span data-ttu-id="3346f-211">での [テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging) について説明 Q# します。</span><span class="sxs-lookup"><span data-stu-id="3346f-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
