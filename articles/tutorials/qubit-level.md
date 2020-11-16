---
title: 'で qubit レベルのプログラムを作成およびシミュレートする Q#'
description: 個々の qubit レベルで動作するクォンタムプログラムの記述とシミュレーションに関するステップバイステップのチュートリアル
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 1bb66ae0fe7de785c417b0bef480e52adea5534d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691715"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="29541-103">チュートリアル: Q で qubit レベルのプログラムを記述してシミュレートする\#</span><span class="sxs-lookup"><span data-stu-id="29541-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="29541-104">個々の qubits で動作する基本的な量子プログラムの作成とシミュレーションに関する、Quantum 開発キットのチュートリアルへようこそ。</span><span class="sxs-lookup"><span data-stu-id="29541-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="29541-105">Q#は主に大規模なクォンタムプログラム用の高レベルのプログラミング言語として作成されていますが、特定の qubits に直接対処するクォンタムプログラムの下位レベルを調べる場合にも簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="29541-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="29541-106">の柔軟性に Q# より、ユーザーはこのような抽象化レベルから量子システムにアプローチできます。このチュートリアルでは、qubits 自体について説明します。</span><span class="sxs-lookup"><span data-stu-id="29541-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="29541-107">具体的には、多くの大きなクォンタムアルゴリズムに不可欠なサブルーチンである [Quantum フーリエ変換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)の内部を見てみます。</span><span class="sxs-lookup"><span data-stu-id="29541-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="29541-108">クォンタム情報処理のこの下位ビューは、システムの特定の qubits に対するゲートの順次アプリケーションを表す "[クォンタム回線](xref:microsoft.quantum.concepts.circuits)" の観点からよく説明されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29541-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="29541-109">したがって、順次適用される単一およびマルチ qubit 操作は、"サーキットダイアグラム" で簡単に表すことができます。</span><span class="sxs-lookup"><span data-stu-id="29541-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="29541-110">ここでは、 Q# 次のような表現をサーキットとして持つ、3つの-qubit クォンタムの完全変換を実行する操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="29541-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="29541-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="29541-111">Prerequisites</span></span>

* <span data-ttu-id="29541-112">任意の言語および開発環境を使用して、Quantum 開発キットを[インストール](xref:microsoft.quantum.install)します。</span><span class="sxs-lookup"><span data-stu-id="29541-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="29541-113">既に QDK をインストールしている場合は、バージョンが[最新](xref:microsoft.quantum.update)であることを確認する</span><span class="sxs-lookup"><span data-stu-id="29541-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="29541-114">このチュートリアルで学習する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29541-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="29541-115">クォンタム操作の定義 Q#</span><span class="sxs-lookup"><span data-stu-id="29541-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="29541-116">Q#コマンドプロンプトから直接、またはクラシックホストプログラムを使用して操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="29541-116">Call Q# operations directly from the command prompt or using a classical host program</span></span>
> * <span data-ttu-id="29541-117">Qubit 割り当てから測定出力へのクォンタム操作をシミュレートします</span><span class="sxs-lookup"><span data-stu-id="29541-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="29541-118">操作全体でクォンタムシステムのシミュレートされた wavefunction がどのように変化するかを観察する</span><span class="sxs-lookup"><span data-stu-id="29541-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="29541-119">Microsoft の Quantum 開発キットでクォンタムプログラムを実行するのは、通常、次の2つの部分で構成されています。</span><span class="sxs-lookup"><span data-stu-id="29541-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="29541-120">プログラム自体は、クォンタムプログラミング言語を使用して実装され、 Q# クォンタムコンピューターまたはクォンタムシミュレーターで実行するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="29541-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="29541-121">次のもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="29541-121">These consist of</span></span> 
    - <span data-ttu-id="29541-122">Q# 操作: クォンタムレジスタに作用するサブルーチン、および</span><span class="sxs-lookup"><span data-stu-id="29541-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="29541-123">Q# functions: クォンタムアルゴリズム内で使用される古典サブルーチン。</span><span class="sxs-lookup"><span data-stu-id="29541-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="29541-124">クォンタムプログラムを呼び出すときに使用するエントリポイントと、実行するターゲットコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="29541-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="29541-125">これは、コマンドプロンプトから直接行うことも、Python や C# などの従来のプログラミング言語で記述されたホストプログラムを使用して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="29541-125">This can be done directly from the command prompt, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="29541-126">このチュートリアルでは、どの方法を使用するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="29541-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="29541-127">Qubits の割り当てとクォンタム操作の定義</span><span class="sxs-lookup"><span data-stu-id="29541-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="29541-128">このチュートリアルの最初の部分では、 Q# 操作を定義します。この操作では、 `Perform3qubitQFT` 3 つの qubits でクォンタムフーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="29541-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="29541-129">さらに、関数を使用して、 [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 3 つの qubit システムのシミュレートされた wavefunction が操作間でどのように変化するかを観察します。</span><span class="sxs-lookup"><span data-stu-id="29541-129">In addition, we will use the [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="29541-130">最初の手順として、 Q# プロジェクトとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29541-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="29541-131">この手順は、プログラムの呼び出しに使用する環境によって異なります。詳細については、それぞれの [インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29541-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="29541-132">ここでは、ファイルのコンポーネントについて順を追って説明しますが、コードは以下の完全なブロックとしても使用できます。</span><span class="sxs-lookup"><span data-stu-id="29541-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="29541-133">他の操作にアクセスするための名前空間 Q#</span><span class="sxs-lookup"><span data-stu-id="29541-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="29541-134">ファイル内では、最初に `NamespaceQFT` コンパイラによってアクセスされる名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="29541-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="29541-135">この操作で既存の操作を使用するには Q# 、関連する `Microsoft.Quantum.<>` 名前空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="29541-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="29541-136">引数と戻り値を使用して操作を定義する</span><span class="sxs-lookup"><span data-stu-id="29541-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="29541-137">次に、操作を定義し `Perform3qubitQFT` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="29541-138">現時点では、この操作は引数を取らず、この例では何---も返されません。この場合、Python では、C# または空のタプルのに類似したオブジェクトを返すことを記述し `Unit` `void` `Tuple[()]` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="29541-139">後で、評価結果の配列を返すようにこの値を変更し、その時点で `Unit` がに置き換えられ `Result[]` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="29541-140">に qubits を割り当てる `using`</span><span class="sxs-lookup"><span data-stu-id="29541-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="29541-141">この操作では Q# 、最初に次のステートメントを使用して、3つの qubits のレジスタを割り当て `using` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="29541-142">では `using` 、qubits は $ \ket $ 状態で自動的に割り当てられ {0} ます。</span><span class="sxs-lookup"><span data-stu-id="29541-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="29541-143">これを確認するには、とを使用します。これにより [`Message(<string>)`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 、文字列とシステムの現在の状態がコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="29541-143">We can verify this by using [`Message(<string>)`](xref:Microsoft.Quantum.Intrinsic.Message) and [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="29541-144">およびの各関数は、 `Message(<string>)` `DumpMachine()` [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:Microsoft.Quantum.Diagnostics) どちらもコンソールに直接出力されます。</span><span class="sxs-lookup"><span data-stu-id="29541-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:Microsoft.Quantum.Diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="29541-145">実際のクォンタム計算と同じよう Q# に、では、qubit 状態に直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="29541-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="29541-146">ただし、では、 `DumpMachine` ターゲットコンピューターの現在の状態が出力されるため、完全な状態シミュレーターと組み合わせて使用すると、デバッグと学習に関する貴重な洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="29541-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="29541-147">シングル qubit および制御ゲートの適用</span><span class="sxs-lookup"><span data-stu-id="29541-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="29541-148">次に、操作自体を構成するゲートを適用します。</span><span class="sxs-lookup"><span data-stu-id="29541-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="29541-149">Q# には、名前空間の操作として多くの基本的なクォンタムゲートが既に含まれてい [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) ますが、これらは例外ではありません。</span><span class="sxs-lookup"><span data-stu-id="29541-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="29541-150">操作内では、呼び出し Q# 可能なものを呼び出すステートメントが順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="29541-150">Within a Q# operation, the statements invoking callables will, of course, be run in sequential order.</span></span>
<span data-ttu-id="29541-151">したがって、最初に適用するゲートは、 [`H`](xref:Microsoft.Quantum.Intrinsic.H) 最初の qubit への (Hadamard) です。</span><span class="sxs-lookup"><span data-stu-id="29541-151">Hence, the first gate to apply is the [`H`](xref:Microsoft.Quantum.Intrinsic.H) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="29541-152">レジスタから特定の qubit に操作を適用する (つまり、配列の1つの) 場合は、 `Qubit` `Qubit[]` 標準のインデックス表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="29541-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="29541-153">そのため、を [`H`](xref:Microsoft.Quantum.Intrinsic.H) レジスタの最初の qubit に適用すると、次のような形式になり `qs` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-153">So, applying the [`H`](xref:Microsoft.Quantum.Intrinsic.H) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="29541-154">`H`(Hadamard) ゲートを個々の qubits に適用するだけでなく、QFT 回線は主に制御された回転で構成され [`R1`](xref:Microsoft.Quantum.Intrinsic.R1) ます。</span><span class="sxs-lookup"><span data-stu-id="29541-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:Microsoft.Quantum.Intrinsic.R1) rotations.</span></span>
<span data-ttu-id="29541-155">`R1(θ, <qubit>)`一般的な操作では、 {0} qubit の $ \ket $ コンポーネントが変更されず、$ \ket $ コンポーネントに $e ^ {i-シータ} $ の回転が適用され {1} ます。</span><span class="sxs-lookup"><span data-stu-id="29541-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="29541-156">制御された操作</span><span class="sxs-lookup"><span data-stu-id="29541-156">Controlled operations</span></span>

<span data-ttu-id="29541-157">Q# を使用すると、1つまたは複数のコントロール qubits に対して操作を実行する条件を非常に簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="29541-157">Q# makes it extremely easy to condition the run of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="29541-158">一般に、を呼び出しの前にを付けるだけで、 `Controlled` 操作の引数は次のように変更されます。</span><span class="sxs-lookup"><span data-stu-id="29541-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="29541-159">`Op(<normal args>)` $ \ から $ `Controlled Op([<control qubits>], (<normal args>))` 。</span><span class="sxs-lookup"><span data-stu-id="29541-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="29541-160">Control qubits が1つの qubits であっても、配列として指定されている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29541-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="29541-161">の後、 `H` 次のゲートが最初の qubit に作用するゲートであることがわかり `R1` ます (さらに、2番目と3番目のゲートによって制御されます)。</span><span class="sxs-lookup"><span data-stu-id="29541-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="29541-162">次を使用してこれらを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="29541-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="29541-163">名前空間の関数を使用して、 [`PI()`](xref:Microsoft.Quantum.Math.PI) pi ラジアンの観点から回転を定義していることに注意 [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) してください。</span><span class="sxs-lookup"><span data-stu-id="29541-163">Note that we use the [`PI()`](xref:Microsoft.Quantum.Math.PI) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="29541-164">さらに、 `Double` `2.0` 整数で除算する `2` と型エラーがスローされるため、(例:) で除算します。</span><span class="sxs-lookup"><span data-stu-id="29541-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="29541-165">`R1(π/2)` と `R1(π/4)` は、 `S` and `T` 演算 (でも) に相当し `Microsoft.Quantum.Intrinsic` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="29541-166">関連 `H` する操作および制御された回転を2番目と3番目の qubits に適用した後、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="29541-167">[`SWAP`](xref:Microsoft.Quantum.Intrinsic.SWAP)回線を完成させるためにゲートを適用するだけです。</span><span class="sxs-lookup"><span data-stu-id="29541-167">we need only apply a [`SWAP`](xref:Microsoft.Quantum.Intrinsic.SWAP) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="29541-168">このことが必要なのは、クォンタムのフーリエ変換の性質によって qubits が逆順に出力されるためです。そのため、スワップにより、サブルーチンをより大きなアルゴリズムにシームレスに統合できます。</span><span class="sxs-lookup"><span data-stu-id="29541-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="29541-169">そのため、次の操作に、クォンタムのフーリエ変換の qubit レベルの操作を記述しました Q# 。</span><span class="sxs-lookup"><span data-stu-id="29541-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="29541-170">ただし、まだ1日に呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="29541-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="29541-171">この qubits は、割り当てられたときに $ \ket $ という州にいましたが、実際には、私たちが発見したのと {0} Q# 同じ方法 (またはより良いもの) にする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="29541-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="29541-172">Qubits の割り当て解除</span><span class="sxs-lookup"><span data-stu-id="29541-172">Deallocate qubits</span></span>

<span data-ttu-id="29541-173">[`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine)もう一度を呼び出して操作後の状態を確認し、最後に [`ResetAll`](xref:Microsoft.Quantum.Intrinsic.resetall) qubit レジスタに適用して、 {0} 操作が完了する前に qubit を $ \ket $ にリセットします。</span><span class="sxs-lookup"><span data-stu-id="29541-173">We call [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:Microsoft.Quantum.Intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="29541-174">すべての割り当て解除された qubits を明示的に $ \ket $ に設定すること {0} は、の基本的な機能です Q# 。これにより、他の操作で同じ qubits (希少リソース) の使用を開始したときに、その状態を正確に知ることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="29541-175">また、これにより、システム内の他の qubits との間では、それらの角度が等しくならないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="29541-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="29541-176">割り当てブロックの最後にリセットが実行されない場合は、 `using` ランタイムエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="29541-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="29541-177">完全な Q# ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="29541-178">Q#ファイルと操作が完了すると、quantum プログラムを呼び出してシミュレートする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="29541-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="29541-179">プログラムを実行する</span><span class="sxs-lookup"><span data-stu-id="29541-179">Run the program</span></span>

<span data-ttu-id="29541-180">ファイルで操作を定義したので、この操作を呼び出して、 Q# `.qs` 返されたすべてのクラシックデータを観察する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29541-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="29541-181">ここでは、返されるものはありません (上記の操作によって定義された操作が返されることを思い出して `Unit` ください) が、後で Q# 測定結果 () の配列を返すように操作を変更する場合 `Result[]` は、このことに対処します。</span><span class="sxs-lookup"><span data-stu-id="29541-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="29541-182">プログラムは、 Q# それを呼び出すために使用される環境全体にわたって普及していますが、そのための方法は当然変わります。</span><span class="sxs-lookup"><span data-stu-id="29541-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="29541-183">そのため、「アプリケーションからの作業」 Q# または「Python または C# でのホストプログラムの使用」に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="29541-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# application or using a host program in Python or C#.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="29541-184">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="29541-184">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="29541-185">Q#コマンドプロンプトからプログラムを実行する場合は、ファイルにわずかな変更しか必要あり Q# ません。</span><span class="sxs-lookup"><span data-stu-id="29541-185">Running the Q# program from the command prompt requires only a small change to the Q# file.</span></span>

<span data-ttu-id="29541-186">`@EntryPoint()`操作の定義の前にある行にを追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="29541-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="29541-187">プログラムを実行するには、プロジェクトのフォルダーにあるターミナルを開き、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="29541-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="29541-188">完了すると、次の出力がコンソールに出力され `Message` `DumpMachine` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-188">Upon completion, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="29541-189">Python</span><span class="sxs-lookup"><span data-stu-id="29541-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="29541-190">Python ホストファイルを作成 `host.py` します。</span><span class="sxs-lookup"><span data-stu-id="29541-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="29541-191">ホストファイルは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="29541-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="29541-192">まず、モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが相互運用性のために登録され Q# ます。</span><span class="sxs-lookup"><span data-stu-id="29541-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="29541-193">これにより、 Q# 名前空間 ( `NamespaceQFT` ファイルで定義されているなど Q# ) が Python モジュールとして表示され、そこから操作をインポートでき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="29541-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="29541-194">次 Q# に、直接呼び出す操作をインポートします。この場合は、--- `Perform3qubitQFT` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="29541-195">エントリポイントをプログラムにインポートする必要がある Q# (つまり、 _not_ `H` `R1` 他の操作によって呼び出され、 Q# クラシックホストによって呼び出されない、やなどの操作がない) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="29541-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="29541-196">Q#操作または関数をシミュレートする場合は、フォームを使用して `<Q#callable>.simulate(<args>)` `QuantumSimulator()` ターゲットコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="29541-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="29541-197">など、別のコンピューターで操作を呼び出す場合は、単にを `ResourceEstimator()` 使用 `<Q#callable>.estimate_resources(<args>)` します。</span><span class="sxs-lookup"><span data-stu-id="29541-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="29541-198">一般に、 Q# 操作は実行されているコンピューターに依存しませんが、などの一部の機能は `DumpMachine` 動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="29541-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="29541-199">シミュレーションを実行すると、操作の呼び出しによって、ファイルで定義されている値が返され Q# ます。</span><span class="sxs-lookup"><span data-stu-id="29541-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="29541-200">ここでは何も返されませんが、後でこれらの値を割り当てて処理する例を確認できます。</span><span class="sxs-lookup"><span data-stu-id="29541-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="29541-201">最終的には、このデータを使用してデータを完成させることができます。</span><span class="sxs-lookup"><span data-stu-id="29541-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="29541-202">完全なファイルは次のようになり `host.py` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="29541-203">Python ファイルを実行してコンソールに出力すると、以下の `Message` 出力と出力が表示され `DumpMachine` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="29541-204">C#</span><span class="sxs-lookup"><span data-stu-id="29541-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="29541-205">[インストールガイド](xref:microsoft.quantum.install.cs)の手順に従って、C# ホストファイルを作成し、名前をに変更し `host.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="29541-206">C# ホストには、次の4つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="29541-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="29541-207">量子シミュレーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="29541-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="29541-208">次のコードでは、これが変数 `qsim` です。</span><span class="sxs-lookup"><span data-stu-id="29541-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="29541-209">量子アルゴリズムに必要な引数を計算します。</span><span class="sxs-lookup"><span data-stu-id="29541-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="29541-210">この例には何もありません。</span><span class="sxs-lookup"><span data-stu-id="29541-210">There are none in this example.</span></span>
3. <span data-ttu-id="29541-211">量子アルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="29541-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="29541-212">各 Q# 操作では、同じ名前の C# クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="29541-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="29541-213">このクラスには、 `Run` 操作を **非同期** に実行するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="29541-213">This class has a `Run` method that runs the operation **asynchronously** .</span></span>
    <span data-ttu-id="29541-214">実際のハードウェアで実行すると非同期に実行されるため、実行は非同期です。</span><span class="sxs-lookup"><span data-stu-id="29541-214">The run is asynchronous because running it on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="29541-215">メソッドは非同期であるため `Run` 、メソッドを呼び出し `Wait()` ます。これにより、タスクが完了するまで実行がブロックされ、同期的に結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="29541-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks the run until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="29541-216">返された操作の結果を処理します。</span><span class="sxs-lookup"><span data-stu-id="29541-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="29541-217">現時点では、操作は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="29541-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="29541-218">アプリケーションを実行します。出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="29541-219">プログラムは、キーを押した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="29541-219">The program will exit after you press a key.</span></span>
<span data-ttu-id="29541-220">\*\*_</span><span class="sxs-lookup"><span data-stu-id="29541-220">\*\*_</span></span>

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="29541-221">完全な状態シミュレーターで呼び出されると、は、 `DumpMachine()` クォンタム状態の wavefunction の複数の表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="29541-221">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="29541-222">$N $-qubit システムの考えられる状態は、それぞれに対応する複合係数 (単なる振幅とフェーズ) を持つ、$ 2 ^ n $ の計算ベースの状態で表すことができます。</span><span class="sxs-lookup"><span data-stu-id="29541-222">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="29541-223">計算ベースの状態は、$---$n 長さのすべての可能なバイナリ文字列に対応します。これは、 {0} {1} 各バイナリ数字が個々の qubit に対応する、qubit 州 $ \ket $ と $ \ket $ のすべての可能な組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="29541-223">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="29541-224">最初の行は、対応する qubits の Id を持つコメントを有意な順序で提供します。</span><span class="sxs-lookup"><span data-stu-id="29541-224">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="29541-225">Qubit が `2` "最も重要" であるということは、基本的な状態ベクトル $ \ket{i} $ のバイナリ表現で、qubit の状態が左端の数字に対応することを意味し `2` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-225">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="29541-226">たとえば、$ \ket {6} = \ket {110} $ は qubits で、$ `2` `1` \ket {1} $ と qubits の両方で `0` $ \ket {0} $ にあります。</span><span class="sxs-lookup"><span data-stu-id="29541-226">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="29541-227">残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{i} $ を測定する確率の振幅を示しています。</span><span class="sxs-lookup"><span data-stu-id="29541-227">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="29541-228">入力状態が $ \ket $: _ の最初の行について詳しく説明します {000} **`|0>:`** 。この行は、計算ベースの状態に対応して `0` います (初期の状態後の割り当てが $ \ket {000} $ である場合、これは、この時点では、これが確率振幅を持つ唯一の状態であると想定されます)。</span><span class="sxs-lookup"><span data-stu-id="29541-228">In detail for the first row of our input state $\ket{000}$: _ **`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="29541-229">**`1.000000 +  0.000000 i`** : デカルト形式の確率の振幅。</span><span class="sxs-lookup"><span data-stu-id="29541-229">**`1.000000 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="29541-230">**` == `** : 符号は、 `equal` 両方の同等の表現を分離します。</span><span class="sxs-lookup"><span data-stu-id="29541-230">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="29541-231">**`********************`** : 大きさをグラフィカルに表示します。の数は、 `*` この状態ベクターを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="29541-231">**`********************`** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="29541-232">**`[ 1.000000 ]`** : マグニチュードの数値</span><span class="sxs-lookup"><span data-stu-id="29541-232">**`[ 1.000000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="29541-233">**`    ---`** : 振幅のフェーズをグラフィカルに表示します。</span><span class="sxs-lookup"><span data-stu-id="29541-233">**`    ---`** : A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="29541-234">**`[ 0.0000 rad ]`** : フェーズの数値 (ラジアン)。</span><span class="sxs-lookup"><span data-stu-id="29541-234">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="29541-235">大きさとフェーズの両方がグラフィック表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="29541-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="29541-236">大きさの表現は簡単です。の棒が表示され、 `*` 確率が高いほど、棒が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="29541-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="29541-237">フェーズについては、「 [テストおよびデバッグ:](xref:microsoft.quantum.guide.testingdebugging#dump-functions) 山の範囲に基づいて可能なシンボル表現のダンプ関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29541-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="29541-238">そのため、この出力は、プログラミングされたゲートによって状態が変換されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="29541-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="29541-239">$ $ \ket{\psi} \_ {initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="29541-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="29541-240">から</span><span class="sxs-lookup"><span data-stu-id="29541-240">to</span></span> 

<span data-ttu-id="29541-241">$ $ \begin{align} \ket{\psi} \_ {final} &= \ frac {1} {\ sqrt {8} } \ 左 (\ket {000} + \ket {001} + \ket + \ket {010} {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} /right) \\ \\ &= \ frac {1} {\ sqrt{2 ^ n}} \ sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="29541-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="29541-242">これは、3つの qubit フーリエ変換の動作です。</span><span class="sxs-lookup"><span data-stu-id="29541-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="29541-243">他の入力状態にどのような影響があるかを知りたい場合は、変換前に qubit 操作を適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29541-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="29541-244">測定値の追加</span><span class="sxs-lookup"><span data-stu-id="29541-244">Adding measurements</span></span>

<span data-ttu-id="29541-245">残念ながら、量子力学の土台として、実際の quantum システムがこのような機能を持つことができないことがわかりました `DumpMachine` 。</span><span class="sxs-lookup"><span data-stu-id="29541-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="29541-246">代わりに、測定値を使用して情報を抽出することが強制されています。これは、完全なクォンタム状態を提供するだけでなく、システム自体を大幅に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="29541-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="29541-247">クォンタム測定にはさまざまな種類がありますが、1つの qubits で最も基本的な射影測定に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="29541-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="29541-248">測定値に基づいて (計算基準 $ \{ \ket {0} 、\ket {1} \} $ など)、qubit 状態は---測定された基準のいずれかの状態に投影されるので、この2つの間の法則は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="29541-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="29541-249">プログラム内で測定を実装するには、 Q# `M` 型を返す操作 (から) を使用し `Microsoft.Quantum.Intrinsic` `Result` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="29541-250">まず、では `Perform3QubitQFT` なく、測定結果の配列を返すように操作を変更 `Result[]` `Unit` します。</span><span class="sxs-lookup"><span data-stu-id="29541-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="29541-251">配列の定義と初期化 `Result[]`</span><span class="sxs-lookup"><span data-stu-id="29541-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="29541-252">(つまり、ステートメントの前に) qubits を割り当てる前に `using` 、次の長さ3の配列を宣言してバインドし `Result` ます (各 qubits に1つ)。</span><span class="sxs-lookup"><span data-stu-id="29541-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="29541-253">前にキーワードを付ける `mutable` と、コードの後で変数を再バインドできるようになり `resultArray` ます。たとえば、測定結果を追加するときに、---ます。</span><span class="sxs-lookup"><span data-stu-id="29541-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="29541-254">ループで測定を実行 `for` し、結果を配列に追加する</span><span class="sxs-lookup"><span data-stu-id="29541-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="29541-255">ブロック内のフーリエ変換操作の後 `using` に、次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="29541-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="29541-256">[`IndexRange`](xref:Microsoft.Quantum.Arrays.IndexRange)配列 (qubits の配列など) で呼び出される関数は、 `qs` 配列のインデックスの範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="29541-256">The [`IndexRange`](xref:Microsoft.Quantum.Arrays.IndexRange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="29541-257">ここでは、ループで使用して、 `for` ステートメントを使用して各 qubit を順番に測定し `M(qs[i])` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="29541-258">各測定 `Result` 型 ( `Zero` または `One` ) は、の対応するインデックス位置に、 `resultArray` 更新と再割り当てのステートメントを使用して追加されます。</span><span class="sxs-lookup"><span data-stu-id="29541-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="29541-259">このステートメントの構文はに固有です Q# が、 `resultArray[i] <- M(qs[i])` F # や R などの他の言語で見られるような変数の再割り当てに相当します。</span><span class="sxs-lookup"><span data-stu-id="29541-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="29541-260">キーワードは、 `set` を使用してバインドされた変数を再割り当てするために常に使用され `mutable` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="29541-261">返し `resultArray`</span><span class="sxs-lookup"><span data-stu-id="29541-261">Return `resultArray`</span></span>

<span data-ttu-id="29541-262">3つの qubits がすべて測定され、結果がに追加されたので `resultArray` 、以前と同じように qubits をリセットし、割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="29541-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="29541-263">`using`ブロックの終了後に、を挿入します。</span><span class="sxs-lookup"><span data-stu-id="29541-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="29541-264">を実行すると、最終的に操作の出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="29541-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="29541-265">測定の効果について</span><span class="sxs-lookup"><span data-stu-id="29541-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="29541-266">`DumpMachine`測定の前後に状態を出力するように関数の配置を変更してみましょう。</span><span class="sxs-lookup"><span data-stu-id="29541-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="29541-267">最終的な操作コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="29541-268">コマンドプロンプトから作業している場合、返された配列は、実行の最後にコンソールに直接表示されます。</span><span class="sxs-lookup"><span data-stu-id="29541-268">If you are working from the command prompt, the returned array will simply be displayed directly to the console at the end of the run.</span></span>
<span data-ttu-id="29541-269">それ以外の場合は、返された配列を処理するようにホストプログラムを更新します。</span><span class="sxs-lookup"><span data-stu-id="29541-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="29541-270">コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="29541-270">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="29541-271">返される配列についての理解を深めるために、コンソールに出力され `Message` Q# ます。次のステートメントの直前に、ファイルにもう1つを追加でき `return` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="29541-272">プロジェクトを実行すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="29541-273">Python</span><span class="sxs-lookup"><span data-stu-id="29541-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="29541-274">Python プログラムを次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="29541-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="29541-275">ファイルを実行すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="29541-276">C#</span><span class="sxs-lookup"><span data-stu-id="29541-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="29541-277">操作が結果を返すようになったので、メソッド呼び出しを `Wait()` プロパティのフェッチに置き換え `Result` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="29541-278">これでも、前に説明したのと同じ同期が得られます。この値を直接変数にバインドすることができ `measurementResult` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="29541-279">プロジェクトを実行すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="29541-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="29541-280">この出力は、次のようないくつかの点を示しています。</span><span class="sxs-lookup"><span data-stu-id="29541-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="29541-281">返された結果を事前測定値と比較する `DumpMachine` と、それ以降の状態に関する QFT 法則は明確に示さ _れません_ 。</span><span class="sxs-lookup"><span data-stu-id="29541-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="29541-282">測定値で返されるのは、システムの wavefunction のその状態の振幅によって決まります。</span><span class="sxs-lookup"><span data-stu-id="29541-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="29541-283">この後の測定値から、測定値によって `DumpMachine` 状態が _変更_ され、基準値に対応する1つの基礎状態に法則の初期状態から投影されます。</span><span class="sxs-lookup"><span data-stu-id="29541-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="29541-284">この操作を何度も繰り返す場合は、結果の統計情報が表示されます。これにより、各ショットに対してランダムな結果が得られる、QFT の状態の法則が均等に重み付けされます。</span><span class="sxs-lookup"><span data-stu-id="29541-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="29541-285">_ただし_ 、非効率的で不完全もありませんが、これによって、基本的な状態の相対的な振幅のみが再現されます。</span><span class="sxs-lookup"><span data-stu-id="29541-285">_However_ , besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="29541-286">後者はこの例では問題ではありませんが、QFT に対するより複雑な入力が $ \ket $ に指定されている場合は、相対フェーズが表示され {000} ます。</span><span class="sxs-lookup"><span data-stu-id="29541-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="29541-287">部分測定</span><span class="sxs-lookup"><span data-stu-id="29541-287">Partial measurements</span></span> 
<span data-ttu-id="29541-288">レジスタの一部の qubits だけを測定してシステムの状態に影響を与える方法を調べるには、 `for` ループ内で、測定行の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="29541-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="29541-289">関数にアクセスするに `IntAsString` は、追加する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29541-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="29541-290">残りの名前空間ステートメントを使用し `open` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="29541-291">結果の出力では、各 qubit が測定されたときに、サブスペースへの段階的な投影が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29541-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="29541-292">ライブラリを使用する Q#</span><span class="sxs-lookup"><span data-stu-id="29541-292">Use the Q# libraries</span></span>
<span data-ttu-id="29541-293">概要で説明したように、のほとんどの機能は、 Q# 個々の qubits を処理する心配をすることができるという事実を備えています。</span><span class="sxs-lookup"><span data-stu-id="29541-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="29541-294">実際には、フルスケールの適用可能なクォンタムプログラムを開発する場合は、 `H` 特定のローテーションの前または後に操作が実行されるかどうかを心配します。</span><span class="sxs-lookup"><span data-stu-id="29541-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="29541-295">これらのライブラリには、 Q# [qft](xref:Microsoft.Quantum.Canon.QFT) 操作が含まれています。この操作は、任意の数の qubits に対して実行して適用することができます。</span><span class="sxs-lookup"><span data-stu-id="29541-295">The Q# libraries contain the [QFT](xref:Microsoft.Quantum.Canon.QFT) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="29541-296">試してみるには、ファイル内にと同じ内容の新しい操作を定義し Q# `Perform3QubitQFT` ます。ただし、最初から2行目までのすべてのものを `H` `SWAP` 置き換えます。</span><span class="sxs-lookup"><span data-stu-id="29541-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="29541-297">最初の行は、 [`BigEndian`](xref:Microsoft.Quantum.Arithmetic.BigEndian) qubits の割り当てられた配列の式を作成するだけです `qs` 。これは、 [qft](xref:Microsoft.Quantum.Canon.QFT) 操作が引数として受け取るものです。</span><span class="sxs-lookup"><span data-stu-id="29541-297">The first line simply creates a [`BigEndian`](xref:Microsoft.Quantum.Arithmetic.BigEndian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:Microsoft.Quantum.Canon.QFT) operation takes as an argument.</span></span>
<span data-ttu-id="29541-298">これは、レジスタ内の qubits のインデックスの順序に対応します。</span><span class="sxs-lookup"><span data-stu-id="29541-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="29541-299">これらの操作にアクセスできるようにするには、 `open` ファイルの先頭にそれぞれの名前空間のステートメントを追加し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="29541-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="29541-300">次に、新しい操作の名前 (例:) を呼び出すようにホストプログラムを調整 `PerformIntrinsicQFT` し、whirl を指定します。</span><span class="sxs-lookup"><span data-stu-id="29541-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="29541-301">ライブラリ操作を使用する実際の利点を確認するには Q# 、次のように qubits の数を変更し `3` ます。</span><span class="sxs-lookup"><span data-stu-id="29541-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4];

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="29541-302">これにより、指定された数の qubits に対して適切な QFT を適用できます。これにより、新しい操作や各 qubits のローテーションについて心配する必要がなく `H` なります。</span><span class="sxs-lookup"><span data-stu-id="29541-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="29541-303">Qubits の数を増やすと、実際の量子ハードウェアに進むために、クォンタムシミュレーターの実行時間が大幅に長くなることに注意してください---</span><span class="sxs-lookup"><span data-stu-id="29541-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>
