---
title: '操作と関数-Q # の手法 |Microsoft Docs'
description: '操作と関数-Q # の手法'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820778"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="cf011-103">Q # 操作と関数</span><span class="sxs-lookup"><span data-stu-id="cf011-103">Q# Operations and Functions</span></span>

<span data-ttu-id="cf011-104">Q # プログラムは、1つまたは複数の操作で構成されています。この*操作*では、クォンタムデータに対して実行できる副作用と、典型的なデータを変更できる1つ以上の*関数*が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf011-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="cf011-105">操作とは対照的に、関数は純粋な古典動作を説明するために使用されます。また、古典出力値の計算以外にも影響はありません。</span><span class="sxs-lookup"><span data-stu-id="cf011-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="cf011-106">Q # で定義された各操作は、その言語で定義されている組み込みの組み込み操作を含む、他の任意の数の操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="cf011-107">これらの組み込み操作が定義されている特定の方法は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cf011-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="cf011-108">コンパイルされると、各操作はターゲットコンピューターに提供できる .NET クラス型として表されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="cf011-109">新しい操作の定義</span><span class="sxs-lookup"><span data-stu-id="cf011-109">Defining New Operations</span></span>

<span data-ttu-id="cf011-110">前に説明したように、Q # で記述されたクォンタムプログラムの最も基本的な構成要素は*操作*であり、たとえば、シミュレーターを使用するか、q # 内の他の操作によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="cf011-111">各操作は、入力を受け取り、出力を生成し、1つまたは複数の操作の特殊化の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf011-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="cf011-112">たとえば、次の操作は、既定の本文の特殊化のみを定義し、入力として1つの qubit を受け取り、その入力に対して組み込みの `X` 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cf011-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="cf011-113">キーワード `operation` によって操作の定義が開始され、その後に名前が付けられます。ここでは、`BitFlip`ます。</span><span class="sxs-lookup"><span data-stu-id="cf011-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="cf011-114">次に、入力の型が `Qubit`として定義され、新しい操作内の入力を参照するための名前 `target` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="cf011-115">同様に、`Unit` は、操作の出力が空であることを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf011-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="cf011-116">これは、 C#とその他の命令型言語の `void` と同様に使用されF#ます。また、とその他の機能言語の `unit` と同じです。</span><span class="sxs-lookup"><span data-stu-id="cf011-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="cf011-117">これについては以下で詳しく説明しますが、Q # の各操作は1つの入力を受け取り、ただ1つの出力を返します。</span><span class="sxs-lookup"><span data-stu-id="cf011-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="cf011-118">複数の入力と出力は、複数の値をまとめて1つの値にまとめる*タプル*を使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="cf011-119">これは、Q # が "タプルインタプル" 言語であるということです。</span><span class="sxs-lookup"><span data-stu-id="cf011-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="cf011-120">この概念に従うと、`Unit`型の "空の" タプルとして `()` を読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf011-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="cf011-121">新しい操作では、既定の本体の特殊化の実装のみを明示的に指定する必要がある場合は、宣言内で実装を直接指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="cf011-122">また、次に示すように、1つ以上の `functor` 操作などのの実装を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf011-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="cf011-123">上記の例では、唯一のステートメントは、組み込みの Q # 操作 <xref:microsoft.quantum.intrinsic.x>を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="cf011-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="cf011-124">操作では、`Unit`よりも興味深い型を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf011-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="cf011-125">たとえば、<xref:microsoft.quantum.intrinsic.m> 操作は、測定を実行したことを表す `Result`型の出力を返します。</span><span class="sxs-lookup"><span data-stu-id="cf011-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="cf011-126">出力を操作から別の操作に渡すことも、`let` キーワードと共に使用して新しい変数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf011-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="cf011-127">これにより、次のように低レベルでクォンタム操作と対話する古典的な計算を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="cf011-128">ファンクター、adjoint、および制御</span><span class="sxs-lookup"><span data-stu-id="cf011-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="cf011-129">操作で、 *adjointed*または*制御*されている場合の操作の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="cf011-130">操作の adjoint 特殊化は、逆の実行時の動作方法を指定し、制御された特殊化は、クォンタムレジスタの状態に適用された場合の操作の動作方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf011-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="cf011-131">これらの特殊化の存在は、次の例の `is Adj + Ctl` 操作シグネチャの一部として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="cf011-132">そのような暗黙的に宣言された各特殊化の対応する実装が、コンパイラによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="cf011-133">Q # の多くの操作は、ユニタリゲートを表します。</span><span class="sxs-lookup"><span data-stu-id="cf011-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="cf011-134">$U $ が、操作 `U`によって表されるユニタリゲートである場合、`Adjoint U` は、$U、ダガー $ のようなユニタリゲートを表します。</span><span class="sxs-lookup"><span data-stu-id="cf011-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="cf011-135">実装がコンパイラによって生成されない場合は、明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="cf011-136">このような明示的な特殊化の宣言は、適切な生成ディレクティブまたはユーザー定義の実装で構成されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="cf011-137">たとえば、上記の `PrepareEntangledPair` のコードは、明示的な特殊化宣言を含む次のコードと同じです。</span><span class="sxs-lookup"><span data-stu-id="cf011-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="cf011-138">キーワード `auto` は、特殊化された実装を生成する方法をコンパイラが決定する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="cf011-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="cf011-139">コンパイラが特定の特殊化の実装を自動的に生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf011-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="cf011-140">上の例では、`adjoint invert;` は、本体の実装を反転することによって adjoint の特殊化が生成されることを示し、`controlled adjoint invert;` は、制御された特殊化の実装を反転することによって、制御された adjoint 特殊化が生成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="cf011-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="cf011-141">これについては、上位の[制御フロー](xref:microsoft.quantum.concepts.control-flow)でさらに例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="cf011-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="cf011-142">操作の特殊化を呼び出すには、`Adjoint` または `Controlled` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf011-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="cf011-143">たとえば、上記の superdense コーディングの例では、`PrepareEntangledPair` の adjoint を使用して、ありの状態を qubits のペアに変換することで、より多くのコンパクトを記述できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="cf011-144">機能を使用するための操作を設計する際に考慮すべき重要な制限がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="cf011-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="cf011-145">他の操作の出力値を使用する操作のために特に特殊化されたものは、コンパイラによって自動的に生成されません。これは、このような操作でステートメントの順序を変更して同じ効果を得る方法があいまいであるためです。</span><span class="sxs-lookup"><span data-stu-id="cf011-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="cf011-146">新しい関数の定義</span><span class="sxs-lookup"><span data-stu-id="cf011-146">Defining New Functions</span></span>

<span data-ttu-id="cf011-147">また、Q # では、関数を定義することもできます。*関数*は、出力値を計算しても影響を与えることができないということです。</span><span class="sxs-lookup"><span data-stu-id="cf011-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="cf011-148">特に、関数は、操作を呼び出したり、qubits に作用したり、乱数をサンプリングしたりすることはできません。また、関数に入力値を超える状態に依存することもあります。</span><span class="sxs-lookup"><span data-stu-id="cf011-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="cf011-149">その結果、Q # 関数は*純粋*に同じ入力値を同じ出力値にマップすることになります。</span><span class="sxs-lookup"><span data-stu-id="cf011-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="cf011-150">これにより、Q # コンパイラは、操作の特殊化を生成するときに関数が呼び出される方法とタイミングを安全に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="cf011-151">関数の定義は、操作を定義する場合と同様に機能します。ただし、関数に対して adjoint または制御された特殊化を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf011-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="cf011-152">その例をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="cf011-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="cf011-153">これを行うには、操作ではなく関数の観点から古典的なロジックを記述することをお勧めします。これにより、操作内からより簡単に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf011-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="cf011-154">たとえば、`Square` を操作として記述した場合、コンパイラは、同じ入力でそれを呼び出すことによって同じ出力が一貫して生成されることを保証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="cf011-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="cf011-155">関数と演算の違いをアンダースコアにするには、Q # 操作内からランダムな数値をサンプリングするクラシックデプロイの問題について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="cf011-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="cf011-156">`U` が呼び出されるたびに、`target`に対して異なる操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="cf011-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="cf011-157">特に、`adjoint auto` 特殊化宣言を `U`に追加した場合、`U(target); Adjoint U(target);` は id として機能することを保証できません (つまり、非 op)。</span><span class="sxs-lookup"><span data-stu-id="cf011-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="cf011-158">これは、[ベクターとマトリックス](xref:microsoft.quantum.concepts.vectors)で見た adjoint の定義に違反しています。これにより、が <xref:microsoft.quantum.math.randomreal> 操作を呼び出したときに、コンパイラによって提供される保証を損なうことがある操作で adjoint 特殊化を自動生成できるようになります。<xref:microsoft.quantum.math.randomreal> は、adjoint または制御されたバージョンが存在しない操作です。</span><span class="sxs-lookup"><span data-stu-id="cf011-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="cf011-159">一方、`Square` などの関数呼び出しを許可しても安全です。そのため、コンパイラは、出力を安定した状態に保つために、`Square` への入力を保持するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="cf011-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="cf011-160">したがって、できるだけ多くの従来のロジックを関数に分離することにより、他の関数や操作でそのロジックを簡単に再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf011-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="cf011-161">制御フロー</span><span class="sxs-lookup"><span data-stu-id="cf011-161">Control Flow</span></span>

<span data-ttu-id="cf011-162">演算または関数内では、最も一般的な命令型の共通言語と同様に、各ステートメントが順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="cf011-163">ただし、この制御フローは、次の3つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="cf011-164">`if` ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf011-164">`if` Statements</span></span>
- <span data-ttu-id="cf011-165">`for` ループ</span><span class="sxs-lookup"><span data-stu-id="cf011-165">`for` Loops</span></span>
- <span data-ttu-id="cf011-166">`repeat`-`until` ループ</span><span class="sxs-lookup"><span data-stu-id="cf011-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="cf011-167">[「成功までの繰り返し (ru)](xref:microsoft.quantum.techniques.qubits#measurements)回線」について説明するまで、後者については説明しません。</span><span class="sxs-lookup"><span data-stu-id="cf011-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="cf011-168">ただし、`if` および `for` 制御フローの構造は、従来のほとんどのプログラミング言語をよく理解しています。</span><span class="sxs-lookup"><span data-stu-id="cf011-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="cf011-169">具体的には、`if` ステートメントは条件を受け取ることができ、その後に1つ以上の `elif` ステートメントが続き、`else`で終わることがあります。</span><span class="sxs-lookup"><span data-stu-id="cf011-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="cf011-170">同様に、`for` ループは、整数の範囲または配列の要素に対する反復処理を示します。</span><span class="sxs-lookup"><span data-stu-id="cf011-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="cf011-171">重要な点として、`for` ループや `if` のステートメントを、特殊化が自動生成される操作で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf011-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="cf011-172">この場合、`for` ループの adjoint は方向を反転し、各反復の adjoint を取ります。</span><span class="sxs-lookup"><span data-stu-id="cf011-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="cf011-173">これは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf011-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="cf011-174">靴を decidedly ている間に、試してみて、お客様の socks を試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="cf011-175">ファーストクラスの値としての操作と関数</span><span class="sxs-lookup"><span data-stu-id="cf011-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="cf011-176">制御フローと従来のロジックについては、操作ではなく関数を使用するという1つの重要な手法として、Q # の操作と関数を*ファーストクラス*で利用することが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="cf011-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="cf011-177">つまり、言語の各値が独自の権限であるということです。</span><span class="sxs-lookup"><span data-stu-id="cf011-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="cf011-178">たとえば、次のコードは完全に有効な Q # コードです (少し間接的な場合)。</span><span class="sxs-lookup"><span data-stu-id="cf011-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="cf011-179">上記のスニペットの変数 `ourH` の値は、他の操作と同様にその値を呼び出すことができるように、操作 <xref:microsoft.quantum.intrinsic.h>になります。</span><span class="sxs-lookup"><span data-stu-id="cf011-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="cf011-180">これにより、高度な制御フローの概念を形成する操作を入力の一部として実行する操作を記述できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="cf011-181">たとえば、同じターゲット qubit に2回適用して、操作を "正方形" にすることを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="cf011-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="cf011-182">この例では、型 `(Qubit => Unit)` に表示される `=>` 矢印は、入力フィールド `op` が `Qubit` 型の入力としてを受け取り、その出力として空のタプルを生成する操作であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="cf011-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="cf011-183">また、サポートされている動作に関する情報を含む、その操作の種類の特性を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf011-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="cf011-184">`(Qubit => Unit)` 型の操作では、`Adjoint` と `Controlled` のファンクタのどちらもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cf011-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="cf011-185">その型の操作が `Adjoint` のファンクタなどをサポートする必要があることを示すには、それを adjointable として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf011-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="cf011-186">これを行うには、型に `is Adj` 注釈を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf011-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="cf011-187">同様に、`(Qubit => Unit is Ctl)` は、その型の操作が `Controlled` のファンクタをサポートしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cf011-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="cf011-188">この詳細については、「Q # での型」 (xref: microsoft. quantum..................................</span><span class="sxs-lookup"><span data-stu-id="cf011-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="cf011-189">ここでは、操作を出力の一部として返すこともできることを強調しています。これは、一部の種類のクラシック条件ロジックを、操作の形式でクォンタムプログラムの説明を返す従来の関数として分離できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="cf011-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="cf011-190">簡単な例として、2ビットの古典的なメッセージを受信するパーティがメッセージを使用して、qubit を適切なテレポートの状態にデコードする必要がある場合の例を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="cf011-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="cf011-191">これは、これらの2つの従来のビットを受け取り、適切なデコード操作を返す関数の観点から記述できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="cf011-192">この新しい関数は実際には関数です。 `hereBit` と `thereBit`の同じ値を使用して呼び出すと、常に同じ操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="cf011-193">そのため、デコードロジックがさまざまな操作の特殊化の定義とどのようにやり取りするかを気にせずに、デコーダーを操作中に安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="cf011-194">つまり、関数内で古典的なロジックを分離し、入力が保持されている限り、関数呼び出しを impunity で並べ替えることができることをコンパイラに保証しています。</span><span class="sxs-lookup"><span data-stu-id="cf011-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="cf011-195">また、関数をファーストクラスの値として扱うこともできます。これは、[操作と関数の種類](#operations-and-functions-as-first-class-values)について詳しく説明する際に、さらに詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="cf011-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="cf011-196">操作と関数の部分的な適用</span><span class="sxs-lookup"><span data-stu-id="cf011-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="cf011-197">*部分的なアプリケーション*を使用して操作を返す関数については、実際には呼び出しを行わずに関数または演算に入力の1つ以上の部分を指定できるようにすることで、さらに多くのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="cf011-198">たとえば、上記の `ApplyTwice` の例を呼び出すと、入力操作が適用される qubit をすぐに指定しなくてもよいことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="cf011-199">この場合、ローカル変数 `twiceOp` は部分的に適用される操作 `ApplyTwice(op, _)`を保持します。この場合、まだ指定されていない入力部分は `_`によって示されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="cf011-200">実際には、次の行で `twiceOp` を呼び出すと、部分的に適用される操作に入力として、入力の残りの部分すべてが元の操作に渡されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="cf011-201">したがって、上記のスニペットは、実際には `ApplyTwice(op, target)` を直接呼び出すのと同じです。新しいローカル変数が導入されています。これにより、入力の一部を提供しながら、呼び出しを遅延させることができます。</span><span class="sxs-lookup"><span data-stu-id="cf011-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="cf011-202">部分的に適用された操作は、入力全体が提供されるまでは実際には呼び出されないため、関数内でも部分的に操作を部分的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf011-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="cf011-203">原則として、`SquareOperation` 内の古典的なロジックははるかに複雑になる可能性がありますが、コンパイラが関数に対して提供できる保証によって、操作の残りの部分から分離されています。</span><span class="sxs-lookup"><span data-stu-id="cf011-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="cf011-204">このアプローチは、一般的な制御フローを、quantum プログラム内で簡単に使用できる方法で表現するために、Q # 標準ライブラリ全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf011-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
