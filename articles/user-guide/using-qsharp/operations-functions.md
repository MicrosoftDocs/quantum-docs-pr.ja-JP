---
title: Q の操作と関数#
description: 操作と関数を定義して呼び出す方法、および制御される操作と adjoint 操作の特殊化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327800"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="19517-103">Q の操作と関数#</span><span class="sxs-lookup"><span data-stu-id="19517-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="19517-104">新しい操作の定義</span><span class="sxs-lookup"><span data-stu-id="19517-104">Defining New Operations</span></span>

<span data-ttu-id="19517-105">操作は Q # の中核です。</span><span class="sxs-lookup"><span data-stu-id="19517-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="19517-106">宣言した後は、たとえばシミュレーターを使用するか、Q # 内の他の操作によって、従来の .NET アプリケーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="19517-107">Q # で定義された各操作は、その言語で定義されている組み込みの組み込み操作を含む、他の任意の数の操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="19517-108">これらの組み込み操作が定義されている特定の方法は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="19517-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="19517-109">コンパイルされると、各操作はターゲットコンピューターに提供できる .NET クラス型として表されます。</span><span class="sxs-lookup"><span data-stu-id="19517-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="19517-110">各 Q # ソースファイルでは、任意の数の操作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="19517-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="19517-111">操作名は名前空間内で一意である必要があり、型または関数名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19517-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="19517-112">操作の宣言は、キーワード、 `operation` その後に操作の名前であるシンボル、操作の引数を定義する型指定された識別子のタプル、コロン `:` 、操作の結果の型を記述する型の注釈、オプションで、操作特性、始めかっこ `{` 、操作宣言の本体、および最後の右中かっこで構成され `}` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="19517-113">各操作は、入力を受け取り、出力を生成し、1つまたは複数の操作の特殊化の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="19517-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="19517-114">有効な特殊化、およびそれらを定義/呼び出す方法については、以下で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="19517-115">ここでは、次の操作について考えてみます。この操作では、既定の本文の特殊化のみが定義され、入力として1つの qubit が使用され、 <xref:microsoft.quantum.intrinsic.x> その入力に対して組み込み演算が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="19517-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="19517-116">キーワードは `operation` 操作の定義を開始し、その後に名前を付けます。ここでは、を指定し `BitFlip` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="19517-117">次に、入力の型がとして `Qubit` 、 `target` 新しい操作内の入力を参照するための名前と共に定義されます。</span><span class="sxs-lookup"><span data-stu-id="19517-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="19517-118">同様に、は、 `Unit` 操作の出力が空であることを定義します。</span><span class="sxs-lookup"><span data-stu-id="19517-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="19517-119">これは、 `void` C# やその他の命令型言語のと同様に使用され、 `unit` F # およびその他の機能言語のと同じです。</span><span class="sxs-lookup"><span data-stu-id="19517-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="19517-120">操作では、より興味深い型も返すことができ `Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="19517-121">たとえば、操作は、 <xref:microsoft.quantum.intrinsic.m> 測定を実行したことを表す型の出力を返し `Result` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="19517-122">操作から別の操作に出力を渡すことも、キーワードを使用して `let` 新しい変数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="19517-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="19517-123">これにより[、次の](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)ように低レベルでクォンタム操作と対話する古典的な計算を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="19517-124">Q # の各操作は、1つの入力だけを受け取り、1つの出力のみを返します。</span><span class="sxs-lookup"><span data-stu-id="19517-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="19517-125">複数の入力と出力は、複数の値をまとめて1つの値にまとめる*タプル*を使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="19517-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="19517-126">これは、Q # が "タプルインタプル" 言語であるということです。</span><span class="sxs-lookup"><span data-stu-id="19517-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="19517-127">この概念に従う `()` と、型を持つ "空の" タプルとして読み取る必要があり `Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="19517-128">制御と Adjoint の操作</span><span class="sxs-lookup"><span data-stu-id="19517-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="19517-129">Q # での多くの操作の場合と同様に、操作によって、 *adjointed*または*制御*されたときの操作の動作を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="19517-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="19517-130">操作の*adjoint*特殊化では、操作の "逆" の動作を指定します。一方、*制御*された特殊化では、そのアプリケーションが特定のクォンタムレジスタの状態に条件を適用する場合の操作方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="19517-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="19517-131">クォンタム操作の adjoints は、クォンタムコンピューティングの多くの側面にとって非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="19517-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="19517-132">さらに、[活用](#conjugations)セクションでは、このような状況について、有用な q&a プログラミング手法と共に紹介します。</span><span class="sxs-lookup"><span data-stu-id="19517-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="19517-133">操作の制御されたバージョンは、すべてのコントロール qubits が指定された状態にある場合にのみ、基本操作を効果的に適用する新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="19517-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="19517-134">コントロール qubits が法則内にある場合、基本操作は一貫の適切な部分に適用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="19517-135">したがって、制御された操作は、多くの場合、entangを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="19517-136">当然ながら、制御された*adjoint*特殊化も存在し、操作の adjoint の制御されたアプリケーションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="19517-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="19517-137">$U $ が、操作によって実装されるユニタリ変換である場合 `U` 、は、 `Adjoint U` $U ^ \ ダガー $ のように、複雑な共役の転置である、この変換を表します。</span><span class="sxs-lookup"><span data-stu-id="19517-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="19517-138">操作を連続して適用した後、その adjoint を状態にしたまま、状態は変更されません。これは、$UU ^ & ダガー = U ^ \ ダガー U = \ id $ (id マトリックス) に示されています。</span><span class="sxs-lookup"><span data-stu-id="19517-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="19517-139">制御された操作のユニタリ表現は少し微妙なですが、「[クォンタムコンピューティングの概念: 複数の qubits](xref:microsoft.quantum.concepts.multiple-qubits)」で詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="19517-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="19517-140">次のセクションでは、これらのさまざまな特殊化を Q # コードで呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="19517-141">以下では、それらをサポートする操作を定義する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="19517-142">呼び出し操作の特殊化</span><span class="sxs-lookup"><span data-stu-id="19517-142">Calling operation specializations</span></span>

<span data-ttu-id="19517-143">Q # の*ファンクタ*は、別の操作から新しい操作を定義するファクトリです。</span><span class="sxs-lookup"><span data-stu-id="19517-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="19517-144">Q # の2つの標準のファンクターは `Adjoint` と `Controlled` です。</span><span class="sxs-lookup"><span data-stu-id="19517-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="19517-145">新しい操作の実装を定義するときに、基本操作の実装にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="19517-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="19517-146">したがって、関数は、従来の上位レベルの関数よりも複雑な関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19517-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="19517-147">この型は、Q # 型システムには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="19517-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="19517-148">そのため、変数にバインドしたり、引数として渡したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="19517-149">ファンクタは、操作に適用して新しい操作を返すことによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="19517-150">たとえば、ファンクタを操作に適用した結果として得られる操作 `Adjoint` は、とし `Y` て書き込まれ `Adjoint Y` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="19517-151">その後、他の操作と同様に、新しい操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="19517-152">またはの機能をサポートする操作の場合 `Adjoint` `Controlled` 、戻り値の型は必ずしもである必要があり `Unit` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="19517-153">`Adjoint`クタ</span><span class="sxs-lookup"><span data-stu-id="19517-153">`Adjoint` functor</span></span>

<span data-ttu-id="19517-154">このため、は、 `Adjoint Y(q1)` Adjoint ファンクタを操作に適用して `Y` 新しい操作を生成し、その新しい操作をに適用し `q1` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="19517-155">新しい操作のシグネチャと型は、基本操作と同じ `Y` です。</span><span class="sxs-lookup"><span data-stu-id="19517-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="19517-156">特に、新しい操作でも許可 `Adjoint` され、基本操作が実行された場合にのみ許可され `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="19517-157">Adjoint ファンクタは、独自の逆になります。つまり、 `Adjoint Adjoint Op` は常にと同じ `Op` です。</span><span class="sxs-lookup"><span data-stu-id="19517-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="19517-158">`Controlled`クタ</span><span class="sxs-lookup"><span data-stu-id="19517-158">`Controlled` functor</span></span>

<span data-ttu-id="19517-159">同様に、は `Controlled X(controls, target)` 制御されたファンクタを操作に適用して `X` 新しい操作を生成し、その新しい操作をとに適用し `controls` `target` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="19517-160">Q # では、制御されたバージョンは常に制御 qubits の配列を受け取り、指定された状態は常に、すべてのコントロール qubits が計算 ( `PauliZ` ) `One` 状態 $ \ket $ に含まれるようになり {1} ます。</span><span class="sxs-lookup"><span data-stu-id="19517-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="19517-161">その他の状態に基づいて制御するには、制御された操作の前に適切なユニタリ操作を制御 qubits に適用し、次に、制御された操作の後に逆を適用します。</span><span class="sxs-lookup"><span data-stu-id="19517-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="19517-162">たとえば、 `X` 制御された操作の前後のコントロール qubit に操作を適用すると、操作は `Zero` その qubit の状態 ($ \ket $) を制御します {0} 。の前後で操作を適用すると、状態が `H` 制御されます。これは、状態では `PauliX` `One` なく、p\ket li X、$ {-} \mathrel{: =} (\ket {0} -\ket {1} )/\ sqrt {2} $ の `PauliZ` `One` -1 の値です。</span><span class="sxs-lookup"><span data-stu-id="19517-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="19517-163">操作式を指定した場合、新しい演算式は、ファンクタを使用して形成される可能性があり `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="19517-164">新しい操作の署名は、元の操作の署名に基づいています。</span><span class="sxs-lookup"><span data-stu-id="19517-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="19517-165">結果の型は同じですが、入力の型は2つのタプルで、最初の要素としてコントロール qubit を保持し、2番目の要素として元の操作の引数を保持します。</span><span class="sxs-lookup"><span data-stu-id="19517-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="19517-166">新しい操作は `Controlled` をサポートし、元の操作が行われた場合にのみをサポートし `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="19517-167">元の操作で1つの引数のみを取得した場合は、シングルトン組の等価性がここで再生されます。</span><span class="sxs-lookup"><span data-stu-id="19517-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="19517-168">たとえば、 `Controlled X` は操作の制御されたバージョンです `X` 。</span><span class="sxs-lookup"><span data-stu-id="19517-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="19517-169">`X`に型がある `(Qubit => Unit is Adj + Ctl)` ため、 `Controlled X` 型があります `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` 。シングルトンタプルの等価性があるため、これはと同じ `((Qubit[], Qubit) => Unit is Adj + Ctl)` です。</span><span class="sxs-lookup"><span data-stu-id="19517-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="19517-170">基本操作に複数の引数を指定する場合は、操作の制御されたバージョンの対応する引数をかっこで囲み、それらをタプルに変換してください。</span><span class="sxs-lookup"><span data-stu-id="19517-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="19517-171">たとえば、 `Controlled Rz` は操作の制御されたバージョンです `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="19517-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="19517-172">`Rz`に型がある `((Double, Qubit) => Unit is Adj + Ctl)` ため、 `Controlled Rz` 型は `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` です。</span><span class="sxs-lookup"><span data-stu-id="19517-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="19517-173">したがって、は `Controlled Rz(controls, (0.1, target))` の有効な呼び出しであると考えら `Controlled Rz` れます (を囲むかっこに注意して `0.1, target` ください)。</span><span class="sxs-lookup"><span data-stu-id="19517-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="19517-174">別の例として、を `CNOT(control, target)` として実装でき `Controlled X([control], target)` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="19517-175">ターゲットを2つの制御 qubits (CCNOT) で制御する必要がある場合は、ステートメントを使用でき `Controlled X([control1, control2], target)` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="19517-176">およびの各ファンクター `Controlled` `Adjoint` commute では、またはの適用に違いはありません `Controlled Adjoint Op` `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="19517-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="19517-177">制御と Adjoint の実装の定義</span><span class="sxs-lookup"><span data-stu-id="19517-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="19517-178">上記の最初の操作宣言の例では、操作 `BitFlip` とは `DecodeSuperdense` それぞれシグネチャとで定義されていました `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="19517-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="19517-179">`DecodeSuperdense`測定値が含まれているため、これは一連の処理ではなく、adjoint 特殊化ではありません (このような操作が返す関連の要件を思い出して `Unit` ください)。</span><span class="sxs-lookup"><span data-stu-id="19517-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="19517-180">ただし、 `BitFlip` 単にユニタリ操作を実行する <xref:microsoft.quantum.intrinsic.x> ため、両方の特殊化を使用して定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="19517-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="19517-181">ここでは、Q # 操作宣言に特殊化の存在を含める方法を説明します。これにより、および/またはのいずれかの機能を使用して呼び出すことができるように `Adjoint` `Controlled` なります。</span><span class="sxs-lookup"><span data-stu-id="19517-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="19517-182">[以下](#circumstances-for-validly-defining-specializations)では、特定の特殊化を宣言するために有効または無効な状況をいくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="19517-183">操作特性は、宣言された操作に適用できる機能の種類と、その効果を定義します。</span><span class="sxs-lookup"><span data-stu-id="19517-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="19517-184">これらの特殊化の存在は、操作のシグネチャの一部として宣言できます。特に、、、のいずれかの操作特性を持つ注釈を使用し `is Adj` `is Ctl` `is Adj + Ctl` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="19517-185">各特殊化の実際の実装は、*暗黙的*または*明示的に*定義することができます。</span><span class="sxs-lookup"><span data-stu-id="19517-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="19517-186">暗黙的な実装の指定</span><span class="sxs-lookup"><span data-stu-id="19517-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="19517-187">この場合、操作宣言の本体は、既定の実装だけで構成されます。</span><span class="sxs-lookup"><span data-stu-id="19517-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="19517-188">例:</span><span class="sxs-lookup"><span data-stu-id="19517-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="19517-189">ここでは、このような暗黙的に宣言されたそれぞれに対応する実装が、またはのいずれかのが使用された場合に実行されるように、コンパイラによって自動的に生成され `Adjoint` `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="19517-190">そのため、の呼び出しに `Adjoint PrepareEntangledPair` より、コンパイラは、の adjoint `CNOT` と、の adjoint を実装し `H` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="19517-191">これらの個々の操作は自己完結型であるため、結果として得られる操作は、 `Adjoint PrepareEntangledPair` とを適用するだけで構成され `CNOT(here, there)` `H(here)` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="19517-192">したがって、これを使用して、コンパクトよりも前の例を記述することができます。これを行うには、 `DecodeSuperdense` の adjoint を使用して、 `PrepareEntangledPair` ありの状態を qubits のペアに変換します。</span><span class="sxs-lookup"><span data-stu-id="19517-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="19517-193">宣言の操作特性を持つ注釈は、コンパイラが既定の実装に基づいて他の特殊化を自動生成するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19517-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="19517-194">機能を使用するための操作を設計する際に考慮すべき重要な制限がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="19517-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="19517-195">他の操作の出力値を使用する操作のために特に特殊化されたものは、コンパイラによって自動的に生成され*ません*。これは、このような操作でステートメントの順序を変更して同じ効果を得る方法があいまいであるためです。</span><span class="sxs-lookup"><span data-stu-id="19517-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="19517-196">そのため、多くの場合、さまざまな実装を明示的に指定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="19517-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="19517-197">明示的な実装の指定</span><span class="sxs-lookup"><span data-stu-id="19517-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="19517-198">実装がコンパイラによって生成されない場合は、明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="19517-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="19517-199">このような明示的な特殊化の宣言は、適切な*生成ディレクティブ*またはユーザー定義の実装で構成されます。</span><span class="sxs-lookup"><span data-stu-id="19517-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="19517-200">ここでは、次の例を使用して、すべての可能性について説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="19517-201">明示的特殊化の宣言</span><span class="sxs-lookup"><span data-stu-id="19517-201">Explicit specialization declarations</span></span>

<span data-ttu-id="19517-202">Q # 操作には、次の明示的特殊化宣言を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="19517-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="19517-203">特殊化は、 `body` 動作が適用されていない操作の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="19517-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="19517-204">特殊化は、 `adjoint` ファンクタが適用された操作の実装を指定し `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="19517-205">特殊化は、 `controlled` ファンクタが適用された操作の実装を指定し `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="19517-206">特殊化は、 `controlled adjoint` との両方が適用された操作の実装を指定し `Adjoint` `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="19517-207">この特殊化は `adjoint controlled` 、2つのファンクター commute から名前を付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="19517-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="19517-208">操作の特殊化は、特殊化タグ (たとえば、やなど) で構成され、 `body` `adjoint` その後に次のいずれかが続きます。</span><span class="sxs-lookup"><span data-stu-id="19517-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="19517-209">明示的な宣言。以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="19517-210">特殊化を生成する*方法*をコンパイラに指示する*ディレクティブ*。次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="19517-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="19517-211">`intrinsic`。ターゲットコンピューターによって特殊化が提供されることを示します。</span><span class="sxs-lookup"><span data-stu-id="19517-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="19517-212">`distribute`。およびの特殊化と共に使用でき `controlled` `controlled adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="19517-213">と共に使用すると、 `controlled` コンパイラは、のすべての操作にを適用することによって、特殊化を計算する必要があることを示し `Controlled` `body` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="19517-214">と共に使用すると、特化された `controlled adjoint` `Controlled` すべての操作にを適用することによって、コンパイラが特殊化を計算する必要があることを示し `adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="19517-215">`invert`。これは、を反転させることによって、コンパイラが特殊化を計算する必要があることを示します `adjoint` `body` 。つまり、操作の順序を逆にし、それぞれに adjoint を適用します。</span><span class="sxs-lookup"><span data-stu-id="19517-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="19517-216">と共に使用すると、コンパイラが特殊化を反転すること `adjoint controlled` によって特殊化を計算する必要があることを示し `controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="19517-217">`self`。これは、adjoint の特殊化が特殊化と同じであることを示してい `body` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="19517-218">これは、および特殊化に対して有効です `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="19517-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="19517-219">の場合 `adjoint controlled` 、 `self` `adjoint controlled` 特殊化は特殊化と同じであることを意味し `controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="19517-220">`auto`。コンパイラが適切なディレクティブを選択して適用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="19517-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="19517-221">`auto`特殊化に使用することはできません `body` 。</span><span class="sxs-lookup"><span data-stu-id="19517-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="19517-222">ディレクティブとすべてには、 `auto` 末尾にセミコロンが必要 `;` です。</span><span class="sxs-lookup"><span data-stu-id="19517-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="19517-223">`auto`の明示的な宣言が指定されている場合、ディレクティブは次のジェネレーションディレクティブに解決され `body` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="19517-224">`adjoint`特殊化は、ディレクティブに応じて生成され `invert` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="19517-225">`controlled`特殊化は、ディレクティブに応じて生成され `distribute` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="19517-226">`adjoint controlled`の明示的な宣言が指定されている場合は、ディレクティブに従って特殊化が生成され `invert` `controlled` `adjoint` `distribute` ます。それ以外の場合は、が使用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="19517-227">操作が自己 adjoint の場合は、generation ディレクティブを使用して adjoint または制御対象の adjoint 特殊化を明示的に指定し、 `self` コンパイラが最適化のためにその情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19517-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="19517-228">ユーザー定義の実装を含む特殊化宣言は、引数の組の後に、特殊化を実装する Q # コードを持つステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="19517-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="19517-229">引数リストでは、 `...` は、操作全体に対して宣言された引数を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="19517-230">とでは、 `body` `adjoint` 引数リストは常にである必要があります `(...)` 。 `controlled` と `adjoint controlled` では、引数リストは、コントロール qubits の配列を表す記号であり、の後に `...` かっこで囲まれたを使用する必要があります (例:) `(controls,...)` 。</span><span class="sxs-lookup"><span data-stu-id="19517-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="19517-231">例</span><span class="sxs-lookup"><span data-stu-id="19517-231">Examples</span></span>

<span data-ttu-id="19517-232">操作の宣言は、次のように単純なものにすることができます。これにより、プリミティブな P# li X 操作が定義されます。</span><span class="sxs-lookup"><span data-stu-id="19517-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="19517-233">P# li X 操作の adjoint がディレクティブで定義されていることに注意して `self` ください。これは、定義によって独自の逆関数が使用されるためです `X` 。</span><span class="sxs-lookup"><span data-stu-id="19517-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="19517-234">上記のコードは、 `PrepareEntangledPair` 明示的な特殊化宣言を含む次のコードと同等です。</span><span class="sxs-lookup"><span data-stu-id="19517-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="19517-235">キーワードは、特殊化された `auto` 実装を生成する方法をコンパイラが決定する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="19517-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="19517-236">ユーザー定義の特殊化の実装</span><span class="sxs-lookup"><span data-stu-id="19517-236">User-defined specialization implementation</span></span>

<span data-ttu-id="19517-237">コンパイラが特定の特殊化の実装を自動的に生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="19517-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="19517-238">上の例では、本体の実装を反転することによって adjoint の特殊化が生成されることを示し、制御された `adjoint invert;` `controlled adjoint invert;` 特殊化の実装を反転することによって、制御された adjoint 特殊化が生成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="19517-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="19517-239">既定の本体以外の1つ以上の特殊化を明示的に宣言する必要がある場合は、既定の本体の実装を適切な特殊化宣言にもラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19517-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="19517-240">特殊化を有効に定義するための状況</span><span class="sxs-lookup"><span data-stu-id="19517-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="19517-241">Adjoint/制御された操作の宣言</span><span class="sxs-lookup"><span data-stu-id="19517-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="19517-242">Adjoint または制御されたバージョンがない操作を指定することはできます。</span><span class="sxs-lookup"><span data-stu-id="19517-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="19517-243">たとえば、測定操作には、反転できるも制御もされないため、どちらもありません。</span><span class="sxs-lookup"><span data-stu-id="19517-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="19517-244">操作は、 `Adjoint` `Controlled` その宣言にそれぞれの特殊化の暗黙的または明示的な宣言が含まれている場合、またはその両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="19517-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="19517-245">明示的に宣言された adjoint/制御された特殊化は、adjoint/制御された特殊化が存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="19517-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="19517-246">本文に繰り返しが有効なループ、set ステートメント、測定、return ステートメント、またはファンクタをサポートしない他の操作への呼び出しが含まれている操作については `Adjoint` 、またはディレクティブの後に adjoint の特殊化を自動生成する `invert` `auto` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="19517-247">ファンクタをサポートしていない他の操作への呼び出しが本文に含まれている操作の場合 `Controlled` 、ディレクティブまたはディレクティブの後で制御される特殊化を自動生成する `distribute` `auto` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="19517-248">制御された Adjoint</span><span class="sxs-lookup"><span data-stu-id="19517-248">Controlled Adjoint</span></span>

<span data-ttu-id="19517-249">操作の制御された adjoint バージョンは、操作のクォンタム制御バージョンを実装する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="19517-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="19517-250">制御されていない adjoint バージョンを持つ操作を指定することはできます。たとえば、測定操作には制御できない、または反転できるではないため、adjoint バージョンは制御されません。</span><span class="sxs-lookup"><span data-stu-id="19517-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="19517-251">操作の制御された adjoint 特殊化は、adjoint と制御対象の両方の特殊化が存在する場合にのみ存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19517-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="19517-252">この場合、制御された adjoint 特殊化の存在が推論され、明示的に定義された実装がない場合は、コンパイラによって適切な特殊化が生成されます。</span><span class="sxs-lookup"><span data-stu-id="19517-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="19517-253">制御された adjoint バージョンを持たない他の操作への呼び出しが本文に含まれている操作の場合、、、またはディレクティブの後の adjoint 特殊化を自動生成する `invert` `distribute` `auto` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="19517-254">型の互換性</span><span class="sxs-lookup"><span data-stu-id="19517-254">Type Compatibility</span></span>

<span data-ttu-id="19517-255">追加のファンクターがサポートされている操作は、より小さい値を持つ操作のすべての場所で使用できますが、同じシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="19517-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="19517-256">たとえば、型の操作が必要な場合は、型の操作を `(Qubit => Unit is Adj)` 使用でき `(Qubit => Unit)` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="19517-257">Q # は呼び出し可能な戻り値の型に関して*共変*です。型を返す呼び出し可能なは、 `'A` 同じ入力型の呼び出し可能なと、と互換性のある結果型と互換性があります `'A` 。</span><span class="sxs-lookup"><span data-stu-id="19517-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="19517-258">Q # は入力型に関して*反変*です。入力として型を受け取る呼び出し可能なは、 `'A` 同じ結果型およびと互換性のある入力型の呼び出しと互換性があり `'A` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="19517-259">つまり、次の定義を指定します。</span><span class="sxs-lookup"><span data-stu-id="19517-259">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="19517-260">次のことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="19517-260">the following are true:</span></span>

- <span data-ttu-id="19517-261">関数は、 `ConjugateInvertWith` `inner` またはの引数を使用して呼び出すことができ `Invert` `ApplyUnitary` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="19517-262">関数は `ConjugateUnitaryWith` 、の引数を指定して呼び出すことができ `inner` `ApplyUnitary` ますが、では呼び出せません `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="19517-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="19517-263">型の値は `(Qubit[] => Unit is Adj + Ctl)` から返される場合があり `ConjugateInvertWith` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19517-264">Q # 0.3 では、ユーザー定義型の動作に大きな違いが導入されました。</span><span class="sxs-lookup"><span data-stu-id="19517-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="19517-265">ユーザー定義型は、サブタイプとしてではなく、基になる型のラップされたバージョンとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="19517-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="19517-266">これは、基になる型の値が必要な場合に、ユーザー定義型の値を使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="19517-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="19517-267">活用</span><span class="sxs-lookup"><span data-stu-id="19517-267">Conjugations</span></span>

<span data-ttu-id="19517-268">従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。</span><span class="sxs-lookup"><span data-stu-id="19517-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="19517-269">これは、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。</span><span class="sxs-lookup"><span data-stu-id="19517-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="19517-270">クォンタムコンピューティングの一般的なパターンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19517-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="19517-271">0.9 リリース以降では、上記の変換を実装する活用形ステートメントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19517-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="19517-272">このステートメントを使用すると、 `ApplyWith` 次のように操作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="19517-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="19517-273">このような活用形ステートメントは、外部と内部の変換を操作として簡単に利用できず、複数のステートメントで構成されるブロックで記述する方が便利な場合に、はるかに便利になります。</span><span class="sxs-lookup"><span data-stu-id="19517-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="19517-274">内部ブロックで定義されたステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="19517-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="19517-275">内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="19517-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="19517-276">新しい関数の定義</span><span class="sxs-lookup"><span data-stu-id="19517-276">Defining New Functions</span></span>

<span data-ttu-id="19517-277">関数は純粋に決定的で、Q # の従来のルーチンです。これは、の操作とは異なり、出力値を計算しても影響を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="19517-278">特に、関数は操作を呼び出すことができません。操作を行う、割り当て、または借りる。乱数の例それ以外の場合は、関数に対する入力値を超えた状態に依存します。</span><span class="sxs-lookup"><span data-stu-id="19517-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="19517-279">その結果、Q # 関数は*純粋*に同じ入力値を同じ出力値にマップすることになります。</span><span class="sxs-lookup"><span data-stu-id="19517-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="19517-280">これにより、Q # コンパイラは、操作の特殊化を生成するときに関数が呼び出される方法とタイミングを安全に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="19517-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="19517-281">各 Q # ソースファイルでは、任意の数の関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="19517-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="19517-282">関数名は、名前空間内で一意である必要があります。また、操作名または型名と競合しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19517-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="19517-283">関数の定義は、操作を定義する場合と同様に機能します。ただし、関数に対して adjoint または制御された特殊化を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="19517-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="19517-284">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19517-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="19517-285">または</span><span class="sxs-lookup"><span data-stu-id="19517-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="19517-286">関数の古典ロジック = = 良好</span><span class="sxs-lookup"><span data-stu-id="19517-286">Classical logic in functions == good</span></span>

<span data-ttu-id="19517-287">これを行うには、操作ではなく関数の観点から古典的なロジックを記述することをお勧めします。これにより、操作内からより簡単に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19517-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="19517-288">たとえば、 `Square` 上記の宣言を*操作*として記述した場合、コンパイラは、同じ入力でそれを呼び出すことによって同じ出力が一貫して生成されることを保証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="19517-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="19517-289">関数と演算の違いをアンダースコアにするには、Q # 操作内からランダムな数値をサンプリングするクラシックデプロイの問題について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="19517-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="19517-290">が呼び出されるたびに `U` 、に対して異なるアクションが行われ `target` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="19517-291">特に、コンパイラは、特殊化宣言をに追加した場合に、id として機能することを保証できません `adjoint auto` `U` `U(target); Adjoint U(target);` (つまり、非 op)。</span><span class="sxs-lookup"><span data-stu-id="19517-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="19517-292">これは、[ベクターとマトリックス](xref:microsoft.quantum.concepts.vectors)で見た adjoint の定義に違反しています。これは、操作を呼び出したときに、コンパイラによって提供される保証を破壊する操作で adjoint 特殊化を自動生成できるようにするためです。 <xref:microsoft.quantum.math.randomreal> は、 <xref:microsoft.quantum.math.randomreal> adjoint または制御バージョンが存在しない操作です。</span><span class="sxs-lookup"><span data-stu-id="19517-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="19517-293">一方、などの関数呼び出し `Square` は安全です。そのため、コンパイラは、出力を安定した状態に保つためにのみ、入力を保持する必要があることを保証でき `Square` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="19517-294">したがって、できるだけ多くの従来のロジックを関数に分離することにより、他の関数や操作でそのロジックを簡単に再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19517-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="19517-295">ジェネリック (型パラメーター化された) 呼び出しの許容型</span><span class="sxs-lookup"><span data-stu-id="19517-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="19517-296">定義する関数や操作の多くは、実際には入力の型にあまり依存していませんが、他の関数や演算を介して暗黙的に型を使用するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="19517-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="19517-297">たとえば、多くの関数言語に共通する*マップ*の概念を考えてみます。関数 $f (x) $ と値 $ x_1、x_2、\ ドット、x_n $ のコレクションが指定されている場合、 \{ \} map は新しいコレクション $ \{ f (x_1)、f (x_2)、\ ドット、f (x_n) $ を返し \} ます。</span><span class="sxs-lookup"><span data-stu-id="19517-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="19517-298">これを Q # に実装するには、その関数を最初のクラスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="19517-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="19517-299">ここ `Map` では、★をプレースホルダーとして使用し、必要な型を確認するという簡単な例を書いてみましょう。</span><span class="sxs-lookup"><span data-stu-id="19517-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="19517-300">注この関数は、どのような実際の型を置き換えるかに関係なく、非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="19517-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="19517-301">たとえば、整数から Paulis へのマップは、浮動小数点数から文字列へのマップとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="19517-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="19517-302">原則として、 `Map` 発生した型のペアごとにのバージョンを記述することもできますが、これには多くの問題が伴います。</span><span class="sxs-lookup"><span data-stu-id="19517-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="19517-303">たとえば、でバグが見つかった場合は、 `Map` すべてのバージョンので、修正プログラムが一様に適用されていることを確認する必要があり `Map` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="19517-304">さらに、新しい組または UDT を構築する場合は、新しい型と共に新しいを作成する必要もあり `Map` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="19517-305">これは、このような関数の少数の扱いですが、と同じ形式の関数を多数収集するので、 `Map` 新しい型の導入にかかるコストは、非常に短い順序で非常になります。</span><span class="sxs-lookup"><span data-stu-id="19517-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="19517-306">しかし、このような問題の多くは、コンパイラによって、のさまざまなバージョンがどのように関連付けられているかを認識するために必要な情報を提供していないからです `Map` 。</span><span class="sxs-lookup"><span data-stu-id="19517-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="19517-307">実際には、コンパイラは `Map` q #*型*から q # 関数に対して何らかの数学的関数として扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19517-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="19517-308">この概念は、関数と操作が*型パラメーター*を持ち、その通常のタプルパラメーターを持つことができるようにすることで形式化されています。</span><span class="sxs-lookup"><span data-stu-id="19517-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="19517-309">上記の例では、最初のケースでは型パラメーターを、2番目のケースではと考える必要が `Map` `Int, Pauli` `Double, String` あります。</span><span class="sxs-lookup"><span data-stu-id="19517-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="19517-310">ほとんどの場合、これらの型パラメーターは通常の型のように使用できます。型パラメーターの値を使用して、配列と組を作成し、関数と演算を呼び出し、通常の変数または変更可能な変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="19517-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="19517-311">間接的な依存関係の最も大きな問題は、qubits の場合です。この場合、Q # プログラムは型の構造に直接依存することはできません `Qubit` が、そのような型を他の操作や関数に渡す**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="19517-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="19517-312">上記の例に戻ると、型パラメーターが必要であることがわかります `Map` 。1つは型パラメーターで、もう1つは、の出力を表すためのもの `fn` `fn` です。</span><span class="sxs-lookup"><span data-stu-id="19517-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="19517-313">Q # では、 `<>` {} 関数または操作の名前の後に山かっこ (つまり、brakets $ \braket $!) を宣言に追加し、それぞれの型パラメーターを一覧表示することによって記述します。</span><span class="sxs-lookup"><span data-stu-id="19517-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="19517-314">各型パラメーターの名前は、型パラメーターであり、 `'` 通常の型 (*具象*型とも呼ばれます) ではないことを示すティックで始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="19517-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="19517-315">`Map`では、次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="19517-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="19517-316">の定義は、前に記述したバージョンと非常によく似ていることに注意 `Map<'Input, 'Output>` してください。</span><span class="sxs-lookup"><span data-stu-id="19517-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="19517-317">唯一の違いは、コンパイラには何かに直接依存しないことを明示的に通知しましたが、を `Map` `'Input` 通じて `'Output` 間接的に使用することで、任意の2つの型に対して機能し `fn` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="19517-318">`Map<'Input, 'Output>`このように定義したら、通常の関数と同じように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="19517-319">ジェネリック関数と操作の記述は、"組イン組アウト" が Q # の関数と演算について考える非常に便利な方法である1つの場所です。</span><span class="sxs-lookup"><span data-stu-id="19517-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="19517-320">すべての関数は1つの入力を受け取り、ただ1つの出力を返すため、型の入力は `'T -> 'U` どの Q # 関数と*も*一致します。</span><span class="sxs-lookup"><span data-stu-id="19517-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="19517-321">同様に、任意の操作を型の入力に渡すこともでき `'T => 'U` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="19517-322">2番目の例として、次の2つの関数の合成を返す関数を記述するという課題を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="19517-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="19517-323">ここでは、、、およびを正確に指定する必要がある `A` `B` ため、 `C` 新しい関数のユーティリティが著しく制限され `Compose` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="19517-324">結局のところ、は、、、 `Compose` およびを介してのみ依存し `A` `B` `C` *via* `innerFn` `outerFn` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="19517-325">別の方法として、型パラメーターをに追加して `Compose` 、*任意*の、、およびで動作することを示すことができます `A` 。これらのパラメーターは、 `B` `C` とで想定されるパラメーターと一致している必要が `innerFn` `outerFn` あります。</span><span class="sxs-lookup"><span data-stu-id="19517-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="19517-326">Q # 標準ライブラリは、このような種類のパラメーター化された操作と関数の範囲を提供して、上位の制御フローを簡単に表現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19517-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="19517-327">これらの詳細については、「 [Q # 標準ライブラリ」ガイド](xref:microsoft.quantum.libraries.standard.intro)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19517-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="19517-328">Callables ファーストクラスの値として指定される</span><span class="sxs-lookup"><span data-stu-id="19517-328">Callables as First-Class Values</span></span>

<span data-ttu-id="19517-329">制御フローと従来のロジックについては、操作ではなく関数を使用するという1つの重要な手法として、Q # の操作と関数を*ファーストクラス*で利用することが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="19517-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="19517-330">つまり、言語の各値が独自の権限であるということです。</span><span class="sxs-lookup"><span data-stu-id="19517-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="19517-331">たとえば、次のコードは完全に有効な Q # コードです (少し間接的な場合)。</span><span class="sxs-lookup"><span data-stu-id="19517-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="19517-332">上記のスニペットの変数の値 `ourH` は操作 <xref:microsoft.quantum.intrinsic.h> であり、他の操作と同様にその値を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="19517-333">これにより、高度な制御フローの概念を形成する操作を入力の一部として実行する操作を記述できます。</span><span class="sxs-lookup"><span data-stu-id="19517-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="19517-334">たとえば、同じターゲット qubit に2回適用して、操作を "正方形" にすることを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="19517-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="19517-335">関数からの操作の返却</span><span class="sxs-lookup"><span data-stu-id="19517-335">Returning operations from a function</span></span>

<span data-ttu-id="19517-336">また、操作を出力の一部として返すこともできることを強調しています。これは、一部の種類のクラシック条件ロジックを、操作の形式でクォンタムプログラムの記述を返す従来の関数として分離できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="19517-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="19517-337">簡単な例として、2ビットの古典的なメッセージを受信するパーティがメッセージを使用して、qubit を適切なテレポートの状態にデコードする必要がある場合の例を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="19517-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="19517-338">これは、これらの2つの従来のビットを受け取り、適切なデコード操作を返す関数の観点から記述できます。</span><span class="sxs-lookup"><span data-stu-id="19517-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="19517-339">この新しい関数は実際には関数です。では、との同じ値を使用して呼び出す `hereBit` と `thereBit` 、常に同じ操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="19517-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="19517-340">そのため、デコードロジックがさまざまな操作の特殊化の定義とどのようにやり取りするかを気にせずに、デコーダーを操作中に安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="19517-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="19517-341">つまり、関数内で古典的なロジックを分離し、入力が保持されている限り、関数呼び出しを impunity で並べ替えることができることをコンパイラに保証しています。</span><span class="sxs-lookup"><span data-stu-id="19517-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="19517-342">部分アプリケーション</span><span class="sxs-lookup"><span data-stu-id="19517-342">Partial Application</span></span>

<span data-ttu-id="19517-343">*部分的なアプリケーション*を使用して操作を返す関数については、実際には呼び出しを行わずに関数または演算に入力の1つ以上の部分を指定できるようにすることで、さらに多くのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="19517-344">たとえば、上記の例を呼び出して、 `ApplyTwice` 入力操作が適用される qubit をすぐに指定しないことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="19517-345">この場合、ローカル変数は部分的に適用された `twiceOp` 操作を保持します。ここでは、まだ指定されて `ApplyTwice(op, _)` いない入力部分がによって示され `_` ます。</span><span class="sxs-lookup"><span data-stu-id="19517-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="19517-346">次の行でを実際に呼び出すときに `twiceOp` 、入力として部分的に適用される操作に入力として、入力の残りの部分すべてを元の操作に渡します。</span><span class="sxs-lookup"><span data-stu-id="19517-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="19517-347">したがって、上記のスニペットは、実際には、直接を呼び出した場合と同じように行われ `ApplyTwice(op, target)` ます。新しいローカル変数を導入したため、入力の一部を提供しながら、呼び出しを遅延させることができます。</span><span class="sxs-lookup"><span data-stu-id="19517-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="19517-348">部分的に適用された操作は、入力全体が提供されるまでは実際には呼び出されないため、関数内でも部分的に操作を部分的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="19517-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="19517-349">原則として、内の従来のロジックははるかに複雑になる `SquareOperation` 可能性がありますが、コンパイラが関数に関して提供できる保証によって、操作の残りの部分から分離されています。</span><span class="sxs-lookup"><span data-stu-id="19517-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="19517-350">このアプローチは、一般的な制御フローを、quantum プログラム内で簡単に使用できる方法で表現するために、Q # 標準ライブラリ全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="19517-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="19517-351">再帰</span><span class="sxs-lookup"><span data-stu-id="19517-351">Recursion</span></span>

<span data-ttu-id="19517-352">Q # callables は、直接的または間接的に再帰的に許可されています。</span><span class="sxs-lookup"><span data-stu-id="19517-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="19517-353">つまり、操作または関数はそれ自体を呼び出すことができます。または、呼び出し可能な操作を直接または間接的に呼び出す別の呼び出し元を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="19517-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="19517-354">ただし、再帰の使用に関しては、次の2つの重要なコメントがあります。</span><span class="sxs-lookup"><span data-stu-id="19517-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="19517-355">操作で再帰を使用すると、特定の最適化が妨げられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19517-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="19517-356">これは、アルゴリズムの実行時間に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19517-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="19517-357">実際のクォンタムデバイスで実行すると、スタック領域が制限される可能性があるため、詳細な再帰によって実行時エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19517-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="19517-358">特に、Q # コンパイラとランタイムは、末尾の再帰を識別して最適化しません。</span><span class="sxs-lookup"><span data-stu-id="19517-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19517-359">次の手順</span><span class="sxs-lookup"><span data-stu-id="19517-359">Next steps</span></span>

<span data-ttu-id="19517-360">Q # の[変数](xref:microsoft.quantum.guide.variables)について説明します。</span><span class="sxs-lookup"><span data-stu-id="19517-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>