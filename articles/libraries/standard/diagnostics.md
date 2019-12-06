---
title: 'Q # 標準ライブラリ-diagnostics |Microsoft Docs'
description: 'Q # 標準ライブラリ-診断'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: d5889b8d5a92801b0ada65f7a17c655c959fc57f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864340"
---
# <a name="diagnostics"></a><span data-ttu-id="a1e45-103">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="a1e45-103">Diagnostics</span></span> #

<span data-ttu-id="a1e45-104">従来の開発と同様に、クォンタムプログラムで間違いやエラーを診断できることが重要です。</span><span class="sxs-lookup"><span data-stu-id="a1e45-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="a1e45-105">Q # 標準ライブラリには、<xref:microsoft.quantum.techniques.testing-and-debugging>で詳しく説明されているように、クォンタムプログラムの正確性を確保するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1e45-105">The Q# standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.techniques.testing-and-debugging>.</span></span>
<span data-ttu-id="a1e45-106">ほとんどの場合、このサポートには、ホストプログラムまたは開発者に追加の診断情報を提供するように対象コンピューターに指示する関数と操作の形式、または条件とインバリアントの正確性を強制的に適用する機能が含まれます。関数または操作の呼び出しによって。</span><span class="sxs-lookup"><span data-stu-id="a1e45-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="a1e45-107">コンピューターの診断</span><span class="sxs-lookup"><span data-stu-id="a1e45-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="a1e45-108"><xref:microsoft.quantum.intrinsic.message> 関数を使用して、コンピューターに依存する方法でメッセージをログに記録することにより、従来の値に関する診断を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-108">Diagnostics about classical values can be obtained by using the <xref:microsoft.quantum.intrinsic.message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="a1e45-109">既定では、文字列がコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="a1e45-110"><xref:microsoft.quantum.intrinsic.message> 補間文字列と共に使用することで、従来の値に関する診断情報を簡単にレポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-110">Used together with interpolated strings, <xref:microsoft.quantum.intrinsic.message> makes it easy to report diagnostic information about classical values:</span></span>

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="a1e45-111">`Message` にはシグネチャ `(String -> Unit)`があります。これに対して、Q # 内からデバッグログメッセージを出力することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1e45-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within Q#.</span></span>

<span data-ttu-id="a1e45-112"><xref:microsoft.quantum.diagnostics.dumpmachine> と <xref:microsoft.quantum.diagnostics.dumpregister> 呼び出しによって、ターゲットマシンは、現在割り当てられている qubits の診断情報、または特定の qubits のレジスタに関する診断情報を提供するように指示します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-112">The <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="a1e45-113">各ターゲットコンピューターは、ダンプ命令への応答として提供される診断情報によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="a1e45-114">たとえば、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)ターゲットコンピューターは、ホストプログラムに対して、内部で使用されて qubits のレジスタを表す状態ベクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="a1e45-115">これに対して、 [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)ターゲットコンピューターは、qubit ごとに1つのクラシックビットを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="a1e45-116">[完全な状態シミュレーターの](xref:microsoft.quantum.machines.full-state-simulator)`DumpMachine` 出力の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)」の記事の「ダンプ関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1e45-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="a1e45-117">ファクトとアサーション</span><span class="sxs-lookup"><span data-stu-id="a1e45-117">Facts and Assertions</span></span> ##

<span data-ttu-id="a1e45-118">「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」で説明したように、シグネチャ `Unit -> Unit` または `Unit => Unit`を持つ関数または操作は、それぞれ*単体テスト*としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.techniques.testing-and-debugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test*.</span></span>
<span data-ttu-id="a1e45-119">各単体テストは、通常、小さいクォンタムプログラムと、そのプログラムの正確性をチェックする1つ以上の条件で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="a1e45-120">これらの条件は、入力の値を確認する_ファクト_、または入力として渡された1つ以上の qubits の状態をチェックする_アサーション_のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-120">These conditions can come in the form of either _facts_, which check the values of their inputs, or _assertions_, which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="a1e45-121">たとえば、`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` は $1 + 1 = $2 の算術事実を表し、`AssertQubit(One, qubit)` は `qubit` を測定して `One` を正確に返す条件を表します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="a1e45-122">前者の場合は、値のみを指定して条件の正確性を確認できます。後者の場合、アサーションを評価するには、qubit の状態に関する情報を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="a1e45-123">Q # 標準ライブラリには、次のようなファクトを表すためのさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1e45-123">The Q# standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfact>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a><span data-ttu-id="a1e45-124">Qubit 状態のテスト</span><span class="sxs-lookup"><span data-stu-id="a1e45-124">Testing Qubit States</span></span> ###

<span data-ttu-id="a1e45-125">実際には、アサーションは、クォンタム機構の古典シミュレーションが、[複製なしの定理](https://arxiv.org/abs/quant-ph/9607018)に従う必要がないという事実に依存しています。これは、ターゲットマシンにシミュレーターを使用するときに、非物理測定とアサーションを行うことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="a1e45-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="a1e45-126">そのため、ハードウェアに展開する前に、古典シミュレーターで個々の操作をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="a1e45-127">アサーションの評価が許可されていないターゲットコンピューターでは、<xref:microsoft.quantum.intrinsic.assert> の呼び出しを無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="a1e45-127">On target machines which do not allow evaluation of assertions, calls to <xref:microsoft.quantum.intrinsic.assert> can be safely ignored.</span></span>

<span data-ttu-id="a1e45-128">一般に、<xref:microsoft.quantum.intrinsic.assert> 操作では、指定された演算子の指定された qubits を測定すると、常に指定された結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-128">More generally, the <xref:microsoft.quantum.intrinsic.assert> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="a1e45-129">アサーションが失敗した場合、指定したメッセージを使用して `fail` を呼び出すことにより、実行が終了します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-129">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="a1e45-130">既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="a1e45-131">`Assert` に署名 `((Pauli[], Qubit[], Result, String) -> ())`があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-131">`Assert` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="a1e45-132">`Assert` は出力型として空のタプルを持つ関数なので、`Assert` を呼び出しても、Q # プログラム内で監視できます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-132">Since `Assert` is a function with an empty tuple as its output type, no effects from having called `Assert` are observable within a Q# program.</span></span>

<span data-ttu-id="a1e45-133"><xref:microsoft.quantum.intrinsic.assertprob> operation 関数は、指定された型の指定された qubits を測定することをアサートします。これは、ある程度の許容範囲内で、指定された確率で特定の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-133">The <xref:microsoft.quantum.intrinsic.assertprob> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="a1e45-134">許容範囲は加法です (例: `abs(expected-actual) < tol`)。</span><span class="sxs-lookup"><span data-stu-id="a1e45-134">Tolerance is additive (e.g. `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="a1e45-135">アサーションが失敗した場合、指定したメッセージを使用して `fail` を呼び出すことにより、実行が終了します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-135">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="a1e45-136">既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="a1e45-137">`AssertProb` に署名 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-137">`AssertProb` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="a1e45-138">最初の `Double` パラメーターは、結果の確率を指定し、2つ目のパラメーターは許容範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="a1e45-139">1つの測定値をアサートする以外にも、シミュレーターで使用される古典的な情報を使用して qubit の内部状態を表すことが、コピーに適しているということを使用します。これは、実際にアサーションをテストするために測定を実行する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="a1e45-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="a1e45-140">具体的には、これにより、実際のハードウェアでは不可能な*互換性*のない測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="a1e45-141">`P : Qubit => Unit` は、入力が $ \ket{0}$ の状態にあるときに、状態 $ \ket{\psi} $ を準備する操作であるとします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="a1e45-142">$ \Ket{\psi '} $ を `P`によって準備された実際の状態にします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="a1e45-143">次に、$ \ket{\psi} = \ket{\psi '} $ は、$ \ket{\psi} $ によって表される軸で $ \ket{\psi '} $ を測定する場合に常に `Zero`を返します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="a1e45-144">つまり、\begin{align} \ket{\psi} = \ket{\psi '} \ text{if と only} \braket{\psi | \ psi '} = 1 です。</span><span class="sxs-lookup"><span data-stu-id="a1e45-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="a1e45-145">\end{align} 準備で定義されているプリミティブ演算を使用して、$ \ket{\psi} $ がいずれかの p Li 演算子の eigenstate である場合は、`Zero` を返す測定値を直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="a1e45-146">操作 <xref:microsoft.quantum.diagnostics.assertqubit> には、アサーション $ \ket{\psi} = \ket{0}$ をテストする場合に特に便利なショートハンドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1e45-146">The operation <xref:microsoft.quantum.diagnostics.assertqubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="a1e45-147">これは一般的に、たとえば、ancilla qubits を $ \ket{0}$ に戻してから解放する場合などです。</span><span class="sxs-lookup"><span data-stu-id="a1e45-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="a1e45-148">$ \Ket{0}$ に対してアサートすることは、2つの状態準備 `P` と `Q` 操作の両方で同じ状態を準備し、`Q` が `Adjoint`をサポートする場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="a1e45-149">特に、</span><span class="sxs-lookup"><span data-stu-id="a1e45-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="a1e45-150">ただし、一般に、Pauli オペレーターの eigenstates と一致しない状態に関するアサーションにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="a1e45-151">たとえば、$ \ket{\psi} = (\ket{0} + e ^ {i \ pi/8} \ket{1})/\ sqrt{2}$ は、Pauli 演算子の eigenstate ではなく、<xref:microsoft.quantum.intrinsic.assertprob> を使用して、状態 $ \ket{\psi '} $ が $ \ket{\psi} $ と等しいことを一意に特定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1e45-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:microsoft.quantum.intrinsic.assertprob> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="a1e45-152">代わりに、アサーション $ \ket{\psi '} = \ket{\psi} $ を、シミュレーターでサポートされているプリミティブを使用して直接テストできる仮定に分解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="a1e45-153">これを行うには、$ \ket{\psi} = \ alpha \ket{0} + \ ベータ \ket{1}$ for complex number $-alpha = a\_r + a\_i i $ and $ \ beta $ とします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="a1e45-154">この式では、各複素数を実数部と虚数部の合計として表すことができるため、\_r、a\_i、b\_r、b\_i\}$ という4つの\{実数が必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a1e45-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="a1e45-155">ただし、グローバルフェーズにより、$a\_i = $0 を選択できます。このような場合、1つの単 qubit 状態を一意に指定するために必要なのは3つの実数だけです。</span><span class="sxs-lookup"><span data-stu-id="a1e45-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="a1e45-156">したがって、予想される状態をアサートするために、互いに独立した3つのアサーションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="a1e45-157">これを行うには、指定された $-alpha $ および $-beta $ に対して `Zero` を観察する確率を調べ、それぞれを独立してアサートします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="a1e45-158">$、$Y $、および $z $ を $x して、それぞれ P# li $X $、$Y $、および $Z $ の測定値を `Result` します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="a1e45-159">次に、クォンタム測定に対して尤度関数を使用して、\begin{align} \ Pr (x = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ (y = \texttt{Zero} | \ アルファ) \ ベータ) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \ Pr (z = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \ 右)。</span><span class="sxs-lookup"><span data-stu-id="a1e45-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="a1e45-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1e45-160">\end{align}</span></span>

<span data-ttu-id="a1e45-161"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 操作では、型 <xref:microsoft.quantum.math.complex>の値として $ \ alpha $ と $ \ beta $ の表現を指定して、これらのアサーションを実装します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-161">The <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:microsoft.quantum.math.complex>.</span></span>
<span data-ttu-id="a1e45-162">これは、予想される状態を数学的に計算できる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a1e45-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="a1e45-163">クォンタム操作が等しいかどうかをアサートしています</span><span class="sxs-lookup"><span data-stu-id="a1e45-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="a1e45-164">これまでに、特定の状態を準備するためのテスト操作について説明しました。</span><span class="sxs-lookup"><span data-stu-id="a1e45-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="a1e45-165">ただし、多くの場合、1つの固定入力ではなく、任意の入力に対して操作がどのように動作するかに注目します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="a1e45-166">たとえば、`adjoint auto`を使用するのではなく、$U (t) $ という一連の `adjoint` に対応する操作 `U : ((Double, Qubit[]) => () : Adjoint)` が実装されているとします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="a1e45-167">$T $ が進化時間を表している場合は、期待どおりに ^ & $U ^ (t) = U (-t) $ をアサートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="a1e45-168">これまでに説明した2つの方法では、2つの操作 `U` し、`V` 動作を同じにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="a1e45-169">まず、`U(target); (Adjoint V)(target);` が各状態を一定の単位で保持していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="a1e45-170">2番目の方法として、ありがある状態の半分に `U(target); (Adjoint V)(target);` 動作することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="a1e45-171">これらの戦略は、それぞれキャノンの操作 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> と <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>によって実装されています。</span><span class="sxs-lookup"><span data-stu-id="a1e45-171">These strategies are implemented by the canon operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> and <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="a1e45-172">前述した参照されているアサーションは、 [Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)に基づいて動作します。このフレームワークでは、$ 2n $ qubits で $n $ qubits に対する操作が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a1e45-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="a1e45-173">特に、$n $ qubits での id 操作は、あり状態 $ \ket{\ beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})//sqrt{2}$ の $n $ コピーによって表されます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="a1e45-174">操作 <xref:microsoft.quantum.preparation.preparechoistate> は、この isomorphism を実装し、指定された操作を表す状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="a1e45-174">The operation <xref:microsoft.quantum.preparation.preparechoistate> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="a1e45-175">大まかに言えば、これらの戦略は時間と領域のトレードオフによって区別されます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="a1e45-176">各入力状態の反復処理には時間がかかりますが、参照として結び付き使用するには追加の qubits を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="a1e45-177">操作によって、計算ベースの状態の動作のみを目的として、元に戻すことができる従来の操作が実装されている場合、<xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> は、この制限された一連の入力で等しいかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="a1e45-178">入力状態に対する反復処理は、列挙操作 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> および <xref:microsoft.quantum.canon.iteratethroughcartesianpower>によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-178">The iteration over input states is handled by the enumeration operations <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> and <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.</span></span>
> <span data-ttu-id="a1e45-179">これらの操作は、通常、2つ以上のセット間でデカルト積の各要素に操作を適用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a1e45-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="a1e45-180">ただし、この2つの方法では、調査中の操作のさまざまなプロパティをテストします。</span><span class="sxs-lookup"><span data-stu-id="a1e45-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="a1e45-181">インプレースアサーションでは各操作が複数回呼び出されるため、各入力状態につき1回、ランダムな選択と測定の結果が呼び出し間で変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1e45-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="a1e45-182">これに対し、参照されるアサーションは、各操作を1回だけ呼び出します。これにより、操作が1回の*ショットで*等しいことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot*.</span></span>
<span data-ttu-id="a1e45-183">これらのテストはどちらも、クォンタムプログラムの正確性を確保するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a1e45-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="a1e45-184">参考情報</span><span class="sxs-lookup"><span data-stu-id="a1e45-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
