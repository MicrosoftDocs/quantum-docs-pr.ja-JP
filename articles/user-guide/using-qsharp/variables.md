---
title: Q# の変数
description: 説明の入力
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430902"
---
# <a name="variables-in-q"></a><span data-ttu-id="1ff0e-103">Q# の変数</span><span class="sxs-lookup"><span data-stu-id="1ff0e-103">Variables in Q#</span></span>

<span data-ttu-id="1ff0e-104">Q# は、変更可能なシンボルと変更できないシンボル、または式にバインド/割り当てられる "variables" を区別します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="1ff0e-105">一般に、変更できないシンボルを使用することをお勧めします。これにより、コンパイラはより多くの最適化を実行できるためです。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="1ff0e-106">バインディングの左側は、記号の組と式の右辺で構成されています。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="1ff0e-107">変更できない変数</span><span class="sxs-lookup"><span data-stu-id="1ff0e-107">Immutable Variables</span></span>

<span data-ttu-id="1ff0e-108">Q# の任意の型の値を変数に代入して、キーワードを使用して操作または関数内で再利用することができ `let` ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="1ff0e-109">変更できないバインドは、キーワードで構成され、 `let` その後にシンボルまたは記号の組、等号 `=` (=)、および終端のセミコロンをバインドする式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="1ff0e-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="1ff0e-111">これにより、P# li の特定の配列が変数名 (または "symbol") に割り当てら `measurementOperator` れます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="1ff0e-112">新しい変数の型を明示的に指定する必要はありませんでした。これは、ステートメントの右辺の式 `let` が明確で、型がコンパイラによって推論されるためです。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="1ff0e-113">を使用して定義された変数 `let` は*変更*できません。つまり、定義されると、どのような方法でも変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="1ff0e-114">これにより、操作のバリアントを適用するために変数に対して動作する古典的なロジックの最適化など、いくつかの有益な最適化が可能に `Adjoint` なります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="1ff0e-115">変更可能な変数</span><span class="sxs-lookup"><span data-stu-id="1ff0e-115">Mutable Variables</span></span>

<span data-ttu-id="1ff0e-116">で変数を作成する代わりに、キーワードを使用して `let` `mutable` 最初に作成した後で再バインド*できる変更可能*な変数を作成し `set` ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="1ff0e-117">ステートメントの一部として宣言およびバインド `mutable` されたシンボルは、コードの後の方で別の値に再バインドされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="1ff0e-118">シンボルが後でコード内で再バインドされる場合、その型は変更されず、新しくバインドされた値はその型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="1ff0e-119">再バインド (変更可能なシンボルの)</span><span class="sxs-lookup"><span data-stu-id="1ff0e-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="1ff0e-120">変更可能な変数は、ステートメントを使用して再バインドすることができ `set` ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="1ff0e-121">このような再バインドは、キーワードと、 `set` その後にシンボルまたは記号の組、等号 (=) を再 `=` バインドする式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="1ff0e-122">ここでは、再バインドステートメントの手法の例をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="1ff0e-123">Apply ステートメントと再割り当てステートメント</span><span class="sxs-lookup"><span data-stu-id="1ff0e-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="1ff0e-124">特定の種類の `set` ステートメントは、*適用および再割り当て*ステートメントとして参照します。右辺が二項演算子のアプリケーションで構成され、結果が演算子の左辺の引数に再バインドされる場合、連結に便利な方法として使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="1ff0e-125">たとえば、オブジェクトに適用された</span><span class="sxs-lookup"><span data-stu-id="1ff0e-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="1ff0e-126">`counter`ループの各反復処理でカウンターの値をインクリメントし `for` ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="1ff0e-127">上記のコードは、</span><span class="sxs-lookup"><span data-stu-id="1ff0e-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="1ff0e-128">左辺の型が式の型と一致するすべての二項演算子に対して、同様のステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="1ff0e-129">これにより、たとえば、値を累積する便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="1ff0e-130">たとえば、 `qubits` 行政、qubits の regsiter です。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="1ff0e-131">更新と再割り当てのステートメント</span><span class="sxs-lookup"><span data-stu-id="1ff0e-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="1ff0e-132">右側には、[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)についても同様の連結が存在します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="1ff0e-133">それに応じて、ユーザー定義型および*配列項目*の*名前付き項目*に対して、*更新と再割り当て*のステートメントが存在します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="1ff0e-134">配列の場合、 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) この標準ライブラリでは、多くの一般的な配列の初期化と操作に必要なツールが提供されるため、最初に配列項目を更新しなくても済むようになります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="1ff0e-135">必要に応じて、更新ステートメントと再割り当てステートメントで代替手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="1ff0e-136">に用意されている配列用のライブラリツールを使用する [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) と、たとえば、Paulis の配列を返す関数を簡単に定義できます。この関数では、インデックスの p li が `i` 指定された値を取得し、他のすべてのエントリが id になります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="1ff0e-137">このような関数の2つの定義を次に示します。2つ目は、ツールを利用することです。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="1ff0e-138">配列内の各インデックスを繰り返し処理するのではなく、条件付きで `PauliI` またはに設定 `Pauli` する代わりに、からを使用しての配列を `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 作成し、 `PauliI` 次にインデックスで特定値を変更したコピーと更新の式を返すだけで済み `location` ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="1ff0e-139">タプル分解</span><span class="sxs-lookup"><span data-stu-id="1ff0e-139">Tuple Deconstruction</span></span>

<span data-ttu-id="1ff0e-140">1つの変数を割り当てることに加えて、 `let` `mutable` キーワードとキーワードは---または実際には (以下で説明するような) 他のバインド構成要素によって、 `set` [タプル型](xref:microsoft.quantum.guide.types#tuple-types)の内容を展開することもでき---ます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="1ff0e-141">このフォームの割り当ては、そのタプルの要素を*分解*と言います。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="1ff0e-142">バインドの右側がタプルの場合、そのタプルは代入時に分解される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="1ff0e-143">このような deconstructions には、入れ子になった組が含まれる場合があります。また、右辺の組の構造がシンボルの組の形状と互換性がある限り、完全または部分的な分解は有効です。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="1ff0e-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="1ff0e-145">スコープのバインド</span><span class="sxs-lookup"><span data-stu-id="1ff0e-145">Binding Scopes</span></span>

<span data-ttu-id="1ff0e-146">一般に、シンボルバインドはスコープ外に出、ステートメントブロックの最後では動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="1ff0e-147">このルールには次の 2 つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="1ff0e-148">ループのループ変数のバインドは、for ループの `for` 本体のスコープ内にありますが、ループの終了後には適用されません。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="1ff0e-149">ループの3つの部分 `repeat` / `until` (本文、テスト、および修正) はすべて1つのスコープとして扱われるので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="1ff0e-150">両方の種類のループでは、ループの各パスが独自のスコープ内で実行されるため、以前のパスからのバインドは、後のパスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="1ff0e-151">これらのループの詳細については、「[制御フロー](xref:microsoft.quantum.guide.controlflow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="1ff0e-152">外部ブロックからのシンボルバインディングは、内部ブロックによって継承されます。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="1ff0e-153">シンボルをバインドできるのは、ブロックごとに1回だけです。スコープ内にある別のシンボルと同じ名前のシンボルを定義することはできません ("シャドウ" はありません)。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="1ff0e-154">有効なシーケンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="1ff0e-155">および</span><span class="sxs-lookup"><span data-stu-id="1ff0e-155">and</span></span>

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

<span data-ttu-id="1ff0e-156">ただし、これは無効になります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="1ff0e-157">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a><span data-ttu-id="1ff0e-158">次の課題</span><span class="sxs-lookup"><span data-stu-id="1ff0e-158">What's Next?</span></span>
<span data-ttu-id="1ff0e-159">Q# での[Qubits の](xref:microsoft.quantum.guide.qubits)使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ff0e-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>
