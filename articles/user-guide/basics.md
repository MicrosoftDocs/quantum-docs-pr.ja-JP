---
title: 'Q # の基本'
description: Q の基本的な概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415363"
---
# <a name="q-basics"></a><span data-ttu-id="f1f83-103">Q # の基本</span><span class="sxs-lookup"><span data-stu-id="f1f83-103">Q# Basics</span></span>

<span data-ttu-id="f1f83-104">この記事では、Q # の基本的な構成要素について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="f1f83-105">どのような Q # があるかの概要と、Quantum 開発キットの基本コンポーネントとしての位置づけについては、「 [q # とは](xref:microsoft.quantum.overview.q-sharp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="f1f83-106">クォンタムプログラムとは</span><span class="sxs-lookup"><span data-stu-id="f1f83-106">What is a quantum program?</span></span>

<span data-ttu-id="f1f83-107">技術的な観点から見ると、quantum プログラムは、特定の一連の従来のサブルーチンであり、これを呼び出すと、クォンタムシステムで特定の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="f1f83-108">このビューの重要な結果として、Q # プログラムは qubits 自体を直接モデル化するのではなく、クラシックデプロイで制御されたコンピューターがこれらの qubits と対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="f1f83-109">仕様により、Q # では、クォンタムの状態やその他の量子機構のプロパティは直接定義されていません。</span><span class="sxs-lookup"><span data-stu-id="f1f83-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="f1f83-110">たとえば、「 {0} {1} {2} [クォンタムコンピューティングの概念](xref:microsoft.quantum.concepts.intro)」ガイドで説明されているように、$ \ket{+} = \ left (\ket + \ket/right)//sqrt $ という状態を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="f1f83-111">この状態を Q # で準備するには、まず、qubits が $ \ket $ 状態で初期化されていることと、$ {0} \ket{+} = H\ket $ という事実を使用し {0} ます。 $H ここで、$ は、 [ `H` 操作](xref:microsoft.quantum.intrinsic.h)によって実装される[Hadamard transform](xref:microsoft.quantum.glossary#hadamard)です。</span><span class="sxs-lookup"><span data-stu-id="f1f83-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="f1f83-112">次のように、qubit を初期化して変換するための基本的な Q # コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="f1f83-113">の初期化、または*割り当て*の詳細については、「 [Qubits の操作](xref:microsoft.quantum.guide.qubits)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-q"></a><span data-ttu-id="f1f83-114">Q でのクォンタムの状態#</span><span class="sxs-lookup"><span data-stu-id="f1f83-114">Quantum states in Q#</span></span>

<span data-ttu-id="f1f83-115">重要な点として、前のプログラムでは、Q # 内の状態を明示的に参照するのではなく、プログラムの状態がどのように*変換*されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="f1f83-116">この方法では、各ターゲットコンピューター上でもクォンタムの状態を完全には認識できません。これは、コンピューターによって*は*、解釈が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1f83-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="f1f83-117">Q # プログラムは、qubit の状態に introspect ことはできません。</span><span class="sxs-lookup"><span data-stu-id="f1f83-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="f1f83-118">代わりに、プログラムはなどの操作を呼び出して、 [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit から情報を取得し、やなどの操作を呼び出して、 [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) qubit の状態を操作できます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="f1f83-119">これらの操作*で*実際に実行されるのは、特定の q&a プログラムを実行するために使用されるターゲットコンピューターのみです。</span><span class="sxs-lookup"><span data-stu-id="f1f83-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="f1f83-120">たとえば、[フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でプログラムを実行すると、シミュレーターはシミュレートされたクォンタムシステムに対応する数学的操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="f1f83-121">しかし、将来的に見てみると、ターゲットコンピューターが実際の quantum のコンピューターである場合、Q # でこのような操作を呼び出すと、*実際*のクォンタムシステムに対応する*実際*の操作 (たとえば、正確に時間がかかるレーザーパルス) を実行するようにクォンタムコンピューターに指示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="f1f83-122">Q # プログラムは、ターゲットコンピューターによって定義されたこれらの操作を結合して、クォンタム計算を表す新しい高レベルの操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="f1f83-123">このように Q # を使用すると、対象のマシンまたはシミュレーターの構造に関しても一般的に、基になるクォンタムやハイブリッドクォンタム–クラシックアルゴリズムを簡単に表現できます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="f1f83-124">Q # 操作と関数</span><span class="sxs-lookup"><span data-stu-id="f1f83-124">Q# operations and functions</span></span>

<span data-ttu-id="f1f83-125">具体的に Q # プログラムは、*操作*、*関数*、および任意のユーザー定義型で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f1f83-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="f1f83-126">操作は、クォンタムシステムの変換を記述するために使用され、Q # プログラムの最も基本的なビルドブロックです。</span><span class="sxs-lookup"><span data-stu-id="f1f83-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="f1f83-127">Q # で定義された各操作は、他の任意の数の操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="f1f83-128">操作とは対照的に、関数は純粋に*決定的*な動作を記述するために使用され、古典的な値の計算以外には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="f1f83-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="f1f83-129">たとえば、プログラムの末尾にある qubits を測定し、測定結果を配列に追加するとします。</span><span class="sxs-lookup"><span data-stu-id="f1f83-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="f1f83-130">この場合、 `Measure` は、ターゲットコンピューターに対して (実際またはシミュレートされた) qubits の測定を実行するように指示する*操作*です。</span><span class="sxs-lookup"><span data-stu-id="f1f83-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="f1f83-131">同時に、*関数*は、返された結果を配列に追加する従来のプロセスを処理します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="f1f83-132">操作と関数は、*呼び出し*が実行できると呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="f1f83-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="f1f83-133">これらの基礎となる構造と動作については、「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="f1f83-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="f1f83-134">Q # 構文の概要</span><span class="sxs-lookup"><span data-stu-id="f1f83-134">Q# syntax overview</span></span>

<span data-ttu-id="f1f83-135">言語の構文では、構文的に正しいプログラムを形成する記号のさまざまな組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="f1f83-136">Q # では、構文要素は、型、式、およびステートメントの3つの異なるグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="f1f83-137">型</span><span class="sxs-lookup"><span data-stu-id="f1f83-137">Types</span></span>
<span data-ttu-id="f1f83-138">Q # は、厳密に型指定された言語であり、型を慎重に使用することで、コンパイラがコンパイル時に Q # プログラムに対する強力な保証を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="f1f83-139">標準およびクォンタム固有の組み込みのプリミティブ型 (、、、など) に加え `Int` て `Bool` `Qubit` `Result` 、Q # ではユーザー定義型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f1f83-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="f1f83-140">すべてのプリミティブ型、配列と組の型の詳細、および Q # ファイル内で新しい型を定義する手順については、「 [q # の型](xref:microsoft.quantum.guide.types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="f1f83-141">式</span><span class="sxs-lookup"><span data-stu-id="f1f83-141">Expressions</span></span>
<span data-ttu-id="f1f83-142">プログラミング言語の式は、プログラミング言語によって解釈され、特定の値に評価される1つ以上の定数、変数、演算子、および関数の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="f1f83-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="f1f83-143">ほとんどの場合、言語のすべての型に対して、その型の式には、*リテラル*またはその型の値にバインドされた記号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="f1f83-144">たとえば、 `5` は `Int` リテラル (つまり型の式) であり、 `Int` 記号 `count` が整数値にバインドされている場合、 `5` `count` は整数式でもあります。</span><span class="sxs-lookup"><span data-stu-id="f1f83-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="f1f83-145">また、式は、特定の演算子で結合された他の式で構成できます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="f1f83-146">たとえば、と `Int` して評価される別の式 `5` は `2+3` です。</span><span class="sxs-lookup"><span data-stu-id="f1f83-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="f1f83-147">Q # の式と互換性のある演算子の詳細については、「 [q # の型式](xref:microsoft.quantum.guide.expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="f1f83-148">ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1f83-148">Statements</span></span> 
<span data-ttu-id="f1f83-149">ステートメントは、実行する何らかのアクションを表す命令型プログラミング言語の構文単位です。ステートメントをそのステートメント内の式と比較すると、結果は返されず、副作用のためだけに実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects.</span></span> <span data-ttu-id="f1f83-150">ただし、式は常に結果を返し、副作用がまったくないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f1f83-150">Expressions, however, always return a result and often do not have side effects at all.</span></span> <span data-ttu-id="f1f83-151">つまり、Q # ステートメントが実行され、式が評価されます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-151">In short, Q# statements are executed, while expressions are evaluated.</span></span>

<span data-ttu-id="f1f83-152">Q # のステートメントの簡単な例では、式に記号を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="f1f83-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="f1f83-153">より興味深い例として、 `for` 反復処理をサポートし、*ステートメントブロック*を含むステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="f1f83-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="f1f83-154">たとえば `qubits` 、記号が qubits のレジスタにバインドされているとします (技術的には、型の `Qubit[]` 場合は、型の配列の場合 `Qubit` )。</span><span class="sxs-lookup"><span data-stu-id="f1f83-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="f1f83-155">Then</span><span class="sxs-lookup"><span data-stu-id="f1f83-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="f1f83-156">レジスタ内の各 qubit を反復処理し、それぞれに対して操作を実行するステートメントです `H` 。</span><span class="sxs-lookup"><span data-stu-id="f1f83-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="f1f83-157">がステートメントでもあることに注意 `H(qubit);` してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="f1f83-158">型の任意の呼び出し式 `Unit` ( `Unit` 型は情報を返さない) をステートメントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="f1f83-159">この型の式は、を返す qubits で操作を呼び出すときに便利です。これは、 `Unit` ステートメントの目的は、暗黙的なクォンタムの状態を変更するためです。</span><span class="sxs-lookup"><span data-stu-id="f1f83-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="f1f83-160">式の評価ステートメントでは、セミコロンを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1f83-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="f1f83-161">ステートメントを使用すると、Q # プログラムのほぼすべての側面を構築できます。また、1つのページに関連するすべての情報を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f1f83-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="f1f83-162">構文の構造と書式設定の詳細については、「 [Q # ファイル構造体](xref:microsoft.quantum.guide.filestructure)」を参照してください。シンボルバインディングの割り当てとスコープについては、「 [Q # の変数](xref:microsoft.quantum.guide.variables)」を参照してください。などの制御フローループについ `for` ては、「 [Q # の制御フロー](xref:microsoft.quantum.guide.controlflow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1f83-163">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f1f83-163">Next steps</span></span>

<span data-ttu-id="f1f83-164">[Q # の型](xref:microsoft.quantum.guide.types)について学習を開始します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="f1f83-165">Q # の背後にある基礎と動機の背景については、「 [q # が必要な理由](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
