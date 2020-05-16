---
title: 'Q # の基本'
description: Q の基本的な概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431157"
---
# <a name="q-basics"></a><span data-ttu-id="73635-103">Q # の基本</span><span class="sxs-lookup"><span data-stu-id="73635-103">Q# Basics</span></span>

<span data-ttu-id="73635-104">このセクションでは、Q # の基本的な構成要素について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="73635-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="73635-105">どのような Q # があるか、および Quantum 開発キットの基本コンポーネントとしてどのような場合に役立つかの概要については、「 [q # とは](xref:microsoft.quantum.overview.q-sharp)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73635-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="73635-106">クォンタムプログラムとは</span><span class="sxs-lookup"><span data-stu-id="73635-106">What is a quantum program?</span></span>

<span data-ttu-id="73635-107">技術的な観点から見ると、クォンタムプログラムは、クォンタムシステムで特定の操作を実行するときに、特定の一連の従来のサブルーチンと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="73635-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="73635-108">このビューの重要な結果として、Q # で記述されたプログラムは、qubits 自体を直接モデル化するのではなく、従来のコントロールコンピューターがその qubits とどのようにやり取りするかを説明します。</span><span class="sxs-lookup"><span data-stu-id="73635-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="73635-109">設計上、Q # では、クォンタムの状態やその他の量子機構のプロパティを直接定義していません。</span><span class="sxs-lookup"><span data-stu-id="73635-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="73635-110">たとえば、「 {0} {1} {2} [クォンタムコンピューティングの概念](xref:microsoft.quantum.concepts.intro)」ガイドで説明されているように、$ \ket{+} = \ left (\ket + \ket/right)//sqrt $ という状態を検討してください。</span><span class="sxs-lookup"><span data-stu-id="73635-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="73635-111">この状態を Q # で準備するには、qubits が $ \ket $ 状態で初期化され、 {0} $ \ket{+} = H\ket $ というファクトを使用し {0} ます。 $H ここで、$ は、[ `H` operation] (] (xref:) によって実装される Hadamard transform です。</span><span class="sxs-lookup"><span data-stu-id="73635-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="73635-112">Q でのクォンタムの状態#</span><span class="sxs-lookup"><span data-stu-id="73635-112">Quantum states in Q#</span></span>

<span data-ttu-id="73635-113">重要なのは、上記のプログラムを作成するときに、Q # 内の状態を明示的に参照するのではなく、その状態がプログラムによってどのように*変換*されたかを説明することです。</span><span class="sxs-lookup"><span data-stu-id="73635-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="73635-114">これにより、各ターゲットコンピューター上でもクォンタムの状態を完全には認識できなくなります。これは、コンピューターによって*は*、解釈が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="73635-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="73635-115">Q # プログラムは、qubit の状態に introspect することはできません。</span><span class="sxs-lookup"><span data-stu-id="73635-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="73635-116">代わりに、プログラムはなどの操作を呼び出して、 [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit から情報を取得したり、やなどの操作を呼び出して [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) qubit の状態を操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="73635-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="73635-117">これらの操作は *、実際には、* 特定の q&a プログラムを実行するために使用するターゲットコンピューターによってのみ具体的に行われます。</span><span class="sxs-lookup"><span data-stu-id="73635-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="73635-118">たとえば、[フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でプログラムを実行すると、シミュレーターはシミュレートされたクォンタムシステムに対応する数学的操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="73635-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="73635-119">しかし、将来的に見てみると、ターゲットコンピューターが実際の quantum のコンピューターである場合、Q # でこのような操作を呼び出すと、*実際*のクォンタムシステムに対応する*実際*の操作を実行するように、クォンタムコンピューターが指示されます (正確に時間がかかるレーザーパルスなど)。</span><span class="sxs-lookup"><span data-stu-id="73635-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="73635-120">Q # プログラムは、ターゲットコンピューターによって定義されたこれらの操作を結合して、クォンタム計算を表す新しい高レベルの操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="73635-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="73635-121">このように Q # を使用すると、対象のマシンまたはシミュレーターの構造に関しても一般的に、基になるクォンタムやハイブリッドクォンタム–クラシックアルゴリズムを簡単に表現できます。</span><span class="sxs-lookup"><span data-stu-id="73635-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="73635-122">Q # 操作と関数</span><span class="sxs-lookup"><span data-stu-id="73635-122">Q# operations and functions</span></span>

<span data-ttu-id="73635-123">具体的に Q # プログラムは、*操作*、*関数*、およびすべてのユーザー定義型で構成されています。</span><span class="sxs-lookup"><span data-stu-id="73635-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="73635-124">操作は、クォンタムシステムの変換を記述するために使用され、Q # プログラムの最も基本的なビルドブロックです。</span><span class="sxs-lookup"><span data-stu-id="73635-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="73635-125">Q # で定義された各操作は、他の任意の数の操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="73635-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="73635-126">操作とは対照的に、関数は純粋に*決定的*な動作を記述するために使用され、古典的な値の計算以外には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="73635-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="73635-127">たとえば、プログラムの末尾にある qubits を測定し、測定結果を配列に追加するとします。</span><span class="sxs-lookup"><span data-stu-id="73635-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="73635-128">この例で `Measure` は、 *operation* (実際のまたはシミュレートされた) qubits の測定を実行するように対象コンピューターに指示し、返された結果を配列に追加する従来のプロセスは*関数*によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="73635-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="73635-129">また、操作と関数は、*呼び出し*が実行できるものと呼ばれ、その基になる構造と動作は[Q # ページの操作と関数](xref:microsoft.quantum.guide.operationsfunctions)で導入されています。</span><span class="sxs-lookup"><span data-stu-id="73635-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="73635-130">Q # 構文の概要</span><span class="sxs-lookup"><span data-stu-id="73635-130">Q# syntax overview</span></span>

<span data-ttu-id="73635-131">言語の構文では、構文的に正しいプログラムを形成する記号のさまざまな組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="73635-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="73635-132">Q # では、3つの異なるグループ (型、式、ステートメント) で構文の要素を分類できます。</span><span class="sxs-lookup"><span data-stu-id="73635-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="73635-133">種類</span><span class="sxs-lookup"><span data-stu-id="73635-133">Types</span></span>
<span data-ttu-id="73635-134">Q # は、厳密に型指定された言語であり、型を慎重に使用することで、コンパイラがコンパイル時に Q # プログラムに対する強力な保証を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73635-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="73635-135">標準およびクォンタム固有の組み込みのプリミティブ型 (、、、など) に加えて `Int` `Bool` `Qubit` `Result` 、Q # ではユーザー定義型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73635-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="73635-136">Q # のさまざまなプリミティブ型については、「Q # の[型」ページで](xref:microsoft.quantum.guide.types)、配列と組の型の詳細と、q # ファイル内で新しい型を定義する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="73635-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="73635-137">式</span><span class="sxs-lookup"><span data-stu-id="73635-137">Expressions</span></span>
<span data-ttu-id="73635-138">プログラミング言語の式は、プログラミング言語によって解釈され、特定の値に評価される1つ以上の定数、変数、演算子、および関数の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="73635-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="73635-139">ほとんどの場合、言語のすべての型に対して、その型の式には、*リテラル*またはその型の値にバインドされた記号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73635-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="73635-140">たとえば、 `5` は `Int` リテラル (つまり型の式) であり、 `Int` 記号 `count` が整数値にバインドされている場合、 `5` `count` は整数式でもあります。</span><span class="sxs-lookup"><span data-stu-id="73635-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="73635-141">また、式は、特定の演算子と組み合わせた他の式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="73635-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="73635-142">そのため、と評価される式のもう1つの例 `Int` `5` は `2+3` です。</span><span class="sxs-lookup"><span data-stu-id="73635-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="73635-143">Q # の型の式と、それらを形成するために使用できる互換性のある演算子の詳細については、 [q # ページの型式](xref:microsoft.quantum.guide.expressions)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73635-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="73635-144">ステートメント</span><span class="sxs-lookup"><span data-stu-id="73635-144">Statements</span></span> 
<span data-ttu-id="73635-145">ステートメントは、実行する何らかのアクションを表す命令型プログラミング言語の構文単位です。ステートメントをそのステートメント内の式と比較すると、結果は返されず、副作用のためだけに実行されます。一方、式は常に結果を返し、副作用はまったくありません。</span><span class="sxs-lookup"><span data-stu-id="73635-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="73635-146">この区別は、多くの場合、式が評価されるのに対し、ステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="73635-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="73635-147">Q # のステートメントの非常に基本的な例は、式に記号を割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="73635-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="73635-148">さらに興味深い例として、 `for` 反復処理をサポートし、*ステートメントブロック*を含むステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="73635-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="73635-149">たとえば `qubits` 、記号が qubits のレジスタにバインドされているとします (技術的には型の `Qubit[]` 配列、つまり型の配列 `Qubit` )。</span><span class="sxs-lookup"><span data-stu-id="73635-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="73635-150">Then</span><span class="sxs-lookup"><span data-stu-id="73635-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="73635-151">は、レジスタ内の各 qubit を反復処理し、 `H` それぞれに対して操作を実行するステートメントです。</span><span class="sxs-lookup"><span data-stu-id="73635-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="73635-152">がステートメントでもあることに注意 `H(qubit);` してください。</span><span class="sxs-lookup"><span data-stu-id="73635-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="73635-153">実際には、型の任意の呼び出し式 `Unit` (情報を返さない型の呼び出し可能な呼び出し) は、ステートメントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="73635-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="73635-154">これは主に、 `Unit` ステートメントの目的が暗黙的なクォンタムの状態を変更するためにを返す qubits で操作を呼び出すときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73635-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="73635-155">式の評価ステートメントでは、セミコロンを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73635-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="73635-156">Q # プログラムのほぼすべての側面がステートメントを使用して構築されているため、1つのページに関連するすべての情報が含まれるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="73635-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="73635-157">ただし、構文の構造と書式設定については、q # の[ファイル構造](xref:microsoft.quantum.guide.filestructure)のページ、 [q # の変数](xref:microsoft.quantum.guide.variables)でのシンボルのバインドの割り当てとスコープ `for` 、 [q # の制御フロー](xref:microsoft.quantum.guide.controlflow)などの制御フローループについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="73635-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>


## <a name="whats-next"></a><span data-ttu-id="73635-158">次の内容</span><span class="sxs-lookup"><span data-stu-id="73635-158">What's next?</span></span>
<span data-ttu-id="73635-159">このガイドの残りの部分では、操作、関数、および型の基本的な構成要素を使用して、Q # を使用して複雑なクォンタムプログラムを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73635-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="73635-160">まず、 [Q # で型](xref:microsoft.quantum.guide.types)について学習を開始できます。</span><span class="sxs-lookup"><span data-stu-id="73635-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="73635-161">Q # の基礎と動機の詳細については、「 [q # が必要な理由](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73635-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
