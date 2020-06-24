---
title: 'Q # 標準ライブラリの診断'
description: 'クォンタムプログラムで間違いやエラーをキャッチするために使用される、Q # 標準ライブラリの診断関数と操作について説明します。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: fa5173f710dd9e0b0b2c110e45aa0bf019111aca
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275704"
---
# <a name="diagnostics"></a><span data-ttu-id="2ed12-103">診断</span><span class="sxs-lookup"><span data-stu-id="2ed12-103">Diagnostics</span></span> #

<span data-ttu-id="2ed12-104">従来の開発と同様に、クォンタムプログラムで間違いやエラーを診断できることが重要です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="2ed12-105">Q # 標準ライブラリには、「」で詳しく説明されているように、クォンタムプログラムの正確性を確保するためのさまざまな方法が用意されて <xref:microsoft.quantum.guide.testingdebugging> います。</span><span class="sxs-lookup"><span data-stu-id="2ed12-105">The Q# standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.guide.testingdebugging>.</span></span>
<span data-ttu-id="2ed12-106">主に、このサポートには、ホストプログラムまたは開発者に追加の診断情報を提供するように対象コンピューターに指示するか、関数または操作の呼び出しで表現される条件と不変性を強制的に適用するための関数と操作の形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="2ed12-107">コンピューターの診断</span><span class="sxs-lookup"><span data-stu-id="2ed12-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="2ed12-108">典型的な値に関する診断は、関数を使用して、 <xref:microsoft.quantum.intrinsic.message> コンピューターに依存する方法でメッセージをログに記録することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-108">Diagnostics about classical values can be obtained by using the <xref:microsoft.quantum.intrinsic.message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="2ed12-109">既定では、文字列がコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="2ed12-110">挿入文字列と共に使用することで、 <xref:microsoft.quantum.intrinsic.message> 従来の値に関する診断情報を簡単にレポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-110">Used together with interpolated strings, <xref:microsoft.quantum.intrinsic.message> makes it easy to report diagnostic information about classical values:</span></span>

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="2ed12-111">`Message`には `(String -> Unit)` 、Q # 内からデバッグログメッセージの出力を確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ed12-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within Q#.</span></span>

<span data-ttu-id="2ed12-112">と呼び出しによって、 <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> ターゲットコンピューターは、現在割り当てられている qubits または特定の qubits のレジスタに関する診断情報をそれぞれ提供するように指示します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-112">The <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="2ed12-113">各ターゲットコンピューターは、ダンプ命令への応答として提供される診断情報によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="2ed12-114">たとえば、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)ターゲットコンピューターは、ホストプログラムに対して、内部で使用されて qubits のレジスタを表す状態ベクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="2ed12-115">これに対して、 [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)ターゲットコンピューターは、qubit ごとに1つのクラシックビットを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="2ed12-116">[完全な状態シミュレーターの](xref:microsoft.quantum.machines.full-state-simulator)出力の詳細については `DumpMachine` 、「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging#dump-functions)」の記事の「ダンプ関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed12-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.guide.testingdebugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="2ed12-117">ファクトとアサーション</span><span class="sxs-lookup"><span data-stu-id="2ed12-117">Facts and Assertions</span></span> ##

<span data-ttu-id="2ed12-118">「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」で説明したように、シグネチャまたはを持つ関数または操作は、 `Unit -> Unit` `Unit => Unit` それぞれ*単体テスト*としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test*.</span></span>
<span data-ttu-id="2ed12-119">各単体テストは、通常、小さいクォンタムプログラムと、そのプログラムの正確性をチェックする1つ以上の条件で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="2ed12-120">これらの条件は、入力の値を確認する_ファクト_、または入力として渡された1つ以上の qubits の状態をチェックする_アサーション_のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-120">These conditions can come in the form of either _facts_, which check the values of their inputs, or _assertions_, which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="2ed12-121">たとえば、は、 `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` $1 + 1 = $2 という数学的な事実を表しますが、は `AssertQubit(One, qubit)` 測定が確実性を `qubit` 持つを返す条件を表し `One` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="2ed12-122">前者の場合は、値のみを指定して条件の正確性を確認できます。後者の場合、アサーションを評価するには、qubit の状態に関する情報を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="2ed12-123">Q # 標準ライブラリには、次のようなファクトを表すためのさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2ed12-123">The Q# standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a><span data-ttu-id="2ed12-124">Qubit 状態のテスト</span><span class="sxs-lookup"><span data-stu-id="2ed12-124">Testing Qubit States</span></span> ###

<span data-ttu-id="2ed12-125">実際には、アサーションは、クォンタム機構の古典シミュレーションが、[複製なしの定理](https://arxiv.org/abs/quant-ph/9607018)に従う必要がないという事実に依存しています。これは、ターゲットマシンにシミュレーターを使用するときに、非物理測定とアサーションを行うことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="2ed12-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="2ed12-126">そのため、ハードウェアに展開する前に、古典シミュレーターで個々の操作をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="2ed12-127">アサーションの評価が許可されていないターゲットコンピューターでは、の呼び出しは <xref:microsoft.quantum.intrinsic.assert> 無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-127">On target machines which do not allow evaluation of assertions, calls to <xref:microsoft.quantum.intrinsic.assert> can be safely ignored.</span></span>

<span data-ttu-id="2ed12-128">一般的に、この操作は、指定されたすべての指定された qubits が指定された <xref:microsoft.quantum.intrinsic.assert> 結果を常に取得することをアサートします。</span><span class="sxs-lookup"><span data-stu-id="2ed12-128">More generally, the <xref:microsoft.quantum.intrinsic.assert> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="2ed12-129">アサーションが失敗した場合、指定したメッセージを使用してを呼び出すことにより、実行が終了し `fail` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-129">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="2ed12-130">既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="2ed12-131">`Assert`に署名があり `((Pauli[], Qubit[], Result, String) -> ())` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-131">`Assert` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="2ed12-132">`Assert`は、出力の種類として空のタプルを持つ関数であるため、を呼び出すことによる影響 `Assert` は、Q # プログラム内では監視できません。</span><span class="sxs-lookup"><span data-stu-id="2ed12-132">Since `Assert` is a function with an empty tuple as its output type, no effects from having called `Assert` are observable within a Q# program.</span></span>

<span data-ttu-id="2ed12-133">操作関数は、指定された型の指定された <xref:microsoft.quantum.intrinsic.assertprob> qubits を測定することをアサートします。これは、一定の許容範囲内で指定された確率で特定の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-133">The <xref:microsoft.quantum.intrinsic.assertprob> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="2ed12-134">許容範囲は加法です (など `abs(expected-actual) < tol` )。</span><span class="sxs-lookup"><span data-stu-id="2ed12-134">Tolerance is additive (e.g. `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="2ed12-135">アサーションが失敗した場合、指定したメッセージを使用してを呼び出すことにより、実行が終了し `fail` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-135">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="2ed12-136">既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="2ed12-137">`AssertProb`に署名があり `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-137">`AssertProb` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="2ed12-138">1つ目のパラメーターは、 `Double` 結果の目的の確率を示し、2番目のパラメーターは許容範囲です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="2ed12-139">1つの測定値をアサートする以外にも、シミュレーターで使用される古典的な情報を使用して qubit の内部状態を表すことが、コピーに適しているということを使用します。これは、実際にアサーションをテストするために測定を実行する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="2ed12-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="2ed12-140">具体的には、これにより、実際のハードウェアでは不可能な*互換性*のない測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="2ed12-141">`P : Qubit => Unit`入力が $ \ket $ という状態にあるときに、状態 $ \ket{\psi} $ を準備する操作であるとし {0} ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="2ed12-142">$ \Ket{\psi '} $ を、によって準備された実際の状態にし `P` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="2ed12-143">$ \Ket{\psi} = \ket{\psi '} $ は、$ \ket{\psi} $ によって記述された軸で $ \ket{\psi '} $ を測定する場合に限り、常にを返し `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="2ed12-144">つまり、\begin{align} \ket{\psi} = \ket{\psi '} \ text{if と only} \braket{\psi | \ psi '} = 1 です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="2ed12-145">\end{align} 準備で定義されているプリミティブ演算を使用して、 `Zero` $ \ket{\psi} $ がいずれかの Pauli 演算子の eigenstate の場合にを返す測定値を直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="2ed12-146">この操作 <xref:microsoft.quantum.diagnostics.assertqubit> には、アサーション $ \ket{\psi} = \ket $ をテストする場合に特に便利なショートハンドが用意されて {0} います。</span><span class="sxs-lookup"><span data-stu-id="2ed12-146">The operation <xref:microsoft.quantum.diagnostics.assertqubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="2ed12-147">これは一般的に、たとえば、ancilla qubits を $ \ket $ に戻してから解放する場合などです {0} 。</span><span class="sxs-lookup"><span data-stu-id="2ed12-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="2ed12-148">$ \Ket $ に対するアサート {0} は、2つの状態 `P` の準備と操作の両方が `Q` 同じ状態を準備し、サポートする場合にも役立ち `Q` `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="2ed12-149">特に、</span><span class="sxs-lookup"><span data-stu-id="2ed12-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="2ed12-150">ただし、一般に、Pauli オペレーターの eigenstates と一致しない状態に関するアサーションにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="2ed12-151">たとえば、$ \ket{\psi} = (\ket {0} + e ^ {i \ pi/8} \ket {1} )/\ sqrt {2} $ は、pauli 演算子の eigenstate ではなく、を使用して <xref:microsoft.quantum.intrinsic.assertprob> 状態 $ \ket{\psi '} $ が $ \ket{\psi} $ と等しいことを一意に特定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ed12-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:microsoft.quantum.intrinsic.assertprob> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="2ed12-152">代わりに、アサーション $ \ket{\psi '} = \ket{\psi} $ を、シミュレーターでサポートされているプリミティブを使用して直接テストできる仮定に分解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="2ed12-153">これを行うには、$ \ket{\psi} = \ alpha \ket {0} + \ beta \ket {1} $ に複素数 $-alpha = a \_ r + a \_ i $ and $ \ beta $ を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="2ed12-154">この式では、 \{ \_ \_ \_ \_ \} 各複素数を実数部と虚数部の合計として表現できるため、$ a r、a i、b r、b i $ という4つの実数が必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2ed12-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="2ed12-155">ただし、グローバルフェーズでは $a \_ i = $0 を選択できます。これにより、1つの単 qubit 状態を一意に指定するために必要なのは、3つの実数だけです。</span><span class="sxs-lookup"><span data-stu-id="2ed12-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="2ed12-156">したがって、予想される状態をアサートするために、互いに独立した3つのアサーションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="2ed12-157">これを行うには、 `Zero` 指定された $-alpha $ および $-beta $ に対して観測する確率を調べ、それぞれを独立してアサートします。</span><span class="sxs-lookup"><span data-stu-id="2ed12-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="2ed12-158">$、$Y $、$z $ be `Result` の値を、それぞれ p$x li $X $、$Y $、および $Z $ の各測定値として使用します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="2ed12-159">次に、クォンタム測定の尤度関数を使用して、\begin{align}/pr (x = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12 + a \_ r b \_ r + a \_ i i \_ \\ \\ Pr (y = \texttt{Zero} |-alpha, \ ベータ) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \ Pr (z = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2)。</span><span class="sxs-lookup"><span data-stu-id="2ed12-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="2ed12-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2ed12-160">\end{align}</span></span>

<span data-ttu-id="2ed12-161">操作は、 <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 型の値として $ \ alpha $ と $ \ beta $ の表現を指定して、これらのアサーションを実装し <xref:microsoft.quantum.math.complex> ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-161">The <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:microsoft.quantum.math.complex>.</span></span>
<span data-ttu-id="2ed12-162">これは、予想される状態を数学的に計算できる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="2ed12-163">クォンタム操作が等しいかどうかをアサートしています</span><span class="sxs-lookup"><span data-stu-id="2ed12-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="2ed12-164">これまでに、特定の状態を準備するためのテスト操作について説明しました。</span><span class="sxs-lookup"><span data-stu-id="2ed12-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="2ed12-165">ただし、多くの場合、1つの固定入力ではなく、任意の入力に対して操作がどのように動作するかに注目します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="2ed12-166">たとえば、 `U : ((Double, Qubit[]) => () : Adjoint)` $U (t) $ というファミリに対応する演算を実装し、を使用する代わりに明示的なブロックを提供したとし `adjoint` `adjoint auto` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="2ed12-167">$T $ が進化時間を表している場合は、期待どおりに ^ & $U ^ (t) = U (-t) $ をアサートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ed12-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="2ed12-168">これまでに説明した2つの方法で、2つの操作を行い、同じように動作させることができ `U` `V` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="2ed12-169">まず、で各状態が保持されていることを確認でき `U(target); (Adjoint V)(target);` ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="2ed12-170">2番目の方法として、力 `U(target); (Adjoint V)(target);` のある状態の半分に作用していることを確認して、その entangを維持します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="2ed12-171">これらの戦略は、それぞれキャノンの操作とによって実装されてい <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-171">These strategies are implemented by the canon operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> and <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="2ed12-172">前述した参照されているアサーションは、 [Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)に基づいて動作します。このフレームワークでは、$ 2n $ qubits で $n $ qubits に対する操作が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="2ed12-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="2ed12-173">特に、$n $ qubits での id 操作は、ありの州 $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ket {11} )/\ sqrt $ の $n $ コピーによって表され {2} ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="2ed12-174">操作は、 <xref:microsoft.quantum.preparation.preparechoistate> この isomorphism を実装し、指定された操作を表す状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="2ed12-174">The operation <xref:microsoft.quantum.preparation.preparechoistate> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="2ed12-175">大まかに言えば、これらの戦略は時間と領域のトレードオフによって区別されます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="2ed12-176">各入力状態の反復処理には時間がかかりますが、参照として結び付き使用するには追加の qubits を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="2ed12-177">操作によって、計算ベースの状態の動作だけを対象として、元に戻すことができる従来の操作が実装されている場合は、 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> この制限付きの入力セットに対して等しいかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="2ed12-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="2ed12-178">入力状態に対する反復処理は、列挙操作およびによって処理され <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> <xref:microsoft.quantum.canon.iteratethroughcartesianpower> ます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-178">The iteration over input states is handled by the enumeration operations <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> and <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.</span></span>
> <span data-ttu-id="2ed12-179">これらの操作は、通常、2つ以上のセット間でデカルト積の各要素に操作を適用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2ed12-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="2ed12-180">ただし、この2つの方法では、調査中の操作のさまざまなプロパティをテストします。</span><span class="sxs-lookup"><span data-stu-id="2ed12-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="2ed12-181">インプレースアサーションでは各操作が複数回呼び出されるため、各入力状態につき1回、ランダムな選択と測定の結果が呼び出し間で変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ed12-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="2ed12-182">これに対し、参照されるアサーションは、各操作を1回だけ呼び出します。これにより、操作が1回の*ショットで*等しいことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot*.</span></span>
<span data-ttu-id="2ed12-183">これらのテストはどちらも、クォンタムプログラムの正確性を確保するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2ed12-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="2ed12-184">もっと読む</span><span class="sxs-lookup"><span data-stu-id="2ed12-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
