---
title: Q の変数#
description: 説明の入力
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885290"
---
# <a name="variables-in-q"></a><span data-ttu-id="c6dae-103">Q の変数#</span><span class="sxs-lookup"><span data-stu-id="c6dae-103">Variables in Q#</span></span>

<span data-ttu-id="c6dae-104">Q # は、変更可能なシンボルと変更できないシンボル、または式にバインド/割り当てられている*変数*を区別します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="c6dae-105">一般に、変更できないシンボルを使用することをお勧めします。これにより、コンパイラはより多くの最適化を実行できるためです。</span><span class="sxs-lookup"><span data-stu-id="c6dae-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="c6dae-106">バインディングの左側は、記号の組と式の右辺で構成されています。</span><span class="sxs-lookup"><span data-stu-id="c6dae-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="c6dae-107">変更できない変数</span><span class="sxs-lookup"><span data-stu-id="c6dae-107">Immutable Variables</span></span>

<span data-ttu-id="c6dae-108">キーワードを使用して、操作または関数内で再利用するために、Q # の任意の型の値を変数に割り当てることができ `let` ます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="c6dae-109">変更できないバインドは、キーワードで構成され、 `let` その後にシンボルまたは記号の組、等号 `=` (=)、および終端のセミコロンをバインドする式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="c6dae-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="c6dae-111">これにより、P# li の特定の配列が変数名 (または "symbol") に割り当てら `measurementOperator` れます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="c6dae-112">前の例では、ステートメントの右辺の式が明確であるため、新しい変数の型を明示的に指定する必要はありません `let` 。コンパイラは正しい型を推論します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="c6dae-113">を使用して定義された変数 `let` は*変更*できません。つまり、変数を定義すると、どのような方法でも変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="c6dae-114">これにより、操作のバリアントを適用するために変数に対して並べ替えを行う従来のロジックの最適化など、いくつかの有益な最適化が可能に `Adjoint` なります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="c6dae-115">変更可能な変数</span><span class="sxs-lookup"><span data-stu-id="c6dae-115">Mutable Variables</span></span>

<span data-ttu-id="c6dae-116">で変数を作成する代わりに、キーワードを使用して `let` `mutable` 最初に作成した後で再バインドできる変更*可能*な変数を作成し `set` ます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="c6dae-117">ステートメントの一部として宣言およびバインドされているシンボルは `mutable` 、後でコード内で別の値に再バインドできます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="c6dae-118">シンボルが後でコード内で再バインドされる場合、その型は変更されず、新しくバインドされた値はその型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="c6dae-119">再バインド (変更可能なシンボルの)</span><span class="sxs-lookup"><span data-stu-id="c6dae-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="c6dae-120">ステートメントを使用して、変更可能な変数を再バインドすることができ `set` ます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="c6dae-121">このような再バインドは、キーワードと、 `set` その後にシンボルまたは記号の組、等号 (=) を再 `=` バインドする式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="c6dae-122">次に、再バインドステートメントの手法の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="c6dae-123">Apply ステートメントと再割り当てステートメント</span><span class="sxs-lookup"><span data-stu-id="c6dae-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="c6dae-124">特定の種類の `set` -ステートメント (*適用および再割り当て*ステートメント) は、右辺が二項演算子のアプリケーションで構成されており、結果が演算子の左辺の引数に再バインドされる場合に、簡単に連結できる方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="c6dae-125">例:</span><span class="sxs-lookup"><span data-stu-id="c6dae-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="c6dae-126">`counter`ループの各反復処理でカウンターの値をインクリメントし `for` ます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="c6dae-127">前のコードはと同じです。</span><span class="sxs-lookup"><span data-stu-id="c6dae-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="c6dae-128">左辺の型が式の型と一致するすべての二項演算子に対して、同様のステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="c6dae-129">これらのステートメントは、値を累積する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="c6dae-130">たとえば、 `qubits` 行政、次のように qubits のレジスタです。</span><span class="sxs-lookup"><span data-stu-id="c6dae-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="c6dae-131">更新と再割り当てのステートメント</span><span class="sxs-lookup"><span data-stu-id="c6dae-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="c6dae-132">右側に[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)がある場合も同様の連結が存在します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="c6dae-133">それに応じて、ユーザー定義型および*配列項目*の*名前付き項目*に対して、*更新と再割り当て*のステートメントが存在します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="c6dae-134">配列の場合、 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Q # 標準ライブラリでは、多くの一般的な配列の初期化と操作に必要なツールが提供されるため、最初に配列項目を更新する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="c6dae-135">必要に応じて、更新ステートメントと再割り当てステートメントで代替手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="c6dae-136">に用意されている配列のライブラリツールを使用すると、 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) たとえば、インデックスの要素が指定された値を `Pauli` `i` 取得し、 `Pauli` その他のすべてのエントリが id () である型の配列を返す関数を簡単に定義でき `PauliI` ます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="c6dae-137">このような関数の2つの定義を次に示します。2つ目は、ツールを利用することです。</span><span class="sxs-lookup"><span data-stu-id="c6dae-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="c6dae-138">配列内の各インデックスを反復処理し、条件付きでまたはに設定するのではなく、を使用して `PauliI` `pauli` `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 型の配列を作成 `PauliI` し、次にインデックスで特定の値を変更したコピーと更新の式を返すだけです `location` 。</span><span class="sxs-lookup"><span data-stu-id="c6dae-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="c6dae-139">タプル分解</span><span class="sxs-lookup"><span data-stu-id="c6dae-139">Tuple Deconstruction</span></span>

<span data-ttu-id="c6dae-140">1つの変数を割り当てるだけでなく、 `let` `mutable` キーワードまたはその他のバインド構成要素 (など) を使用して、 `set` [タプル型](xref:microsoft.quantum.guide.types#tuple-types)の内容をアンパックできます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="c6dae-141">このフォームの割り当ては、そのタプルの要素を*分解*と言います。</span><span class="sxs-lookup"><span data-stu-id="c6dae-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="c6dae-142">バインドの右側がタプルの場合は、代入時にそのタプルを分解できます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="c6dae-143">このような deconstructions には、入れ子になった組を含めることができます。また、右辺の組の構造がシンボルの組の形状と互換性がある限り、完全または部分的な分解は有効です。</span><span class="sxs-lookup"><span data-stu-id="c6dae-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="c6dae-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="c6dae-145">スコープのバインド</span><span class="sxs-lookup"><span data-stu-id="c6dae-145">Binding Scopes</span></span>

<span data-ttu-id="c6dae-146">一般に、シンボルバインドはスコープ外に出、ステートメントブロックの最後では動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="c6dae-147">このルールには次の 2 つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="c6dae-148">ループのループ変数のバインドは、for ループの `for` 本体のスコープ内にありますが、ループの終了後には適用されません。</span><span class="sxs-lookup"><span data-stu-id="c6dae-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="c6dae-149">ループの3つの部分 `repeat` / `until` (本文、テスト、および修正) はすべて1つのスコープとして機能するので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6dae-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="c6dae-150">両方の種類のループでは、ループの各パスが独自のスコープ内で実行されるため、以前のパスからのバインドは、後のパスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c6dae-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="c6dae-151">これらのループの詳細については、「[制御フロー](xref:microsoft.quantum.guide.controlflow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6dae-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="c6dae-152">内部ブロックは、外側のブロックからシンボルバインドを継承します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="c6dae-153">シンボルをバインドできるのは、ブロックごとに1回だけです。スコープ内にある別のシンボルと同じ名前のシンボルを定義することはできません ("シャドウ" はありません)。</span><span class="sxs-lookup"><span data-stu-id="c6dae-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="c6dae-154">有効なシーケンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6dae-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="c6dae-155">および</span><span class="sxs-lookup"><span data-stu-id="c6dae-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="c6dae-156">ただし、これは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="c6dae-157">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c6dae-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="c6dae-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="c6dae-158">Next steps</span></span>

<span data-ttu-id="c6dae-159">Q # での[Qubits の](xref:microsoft.quantum.guide.qubits)使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6dae-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>