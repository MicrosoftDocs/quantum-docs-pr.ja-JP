---
title: 'Q # Introdution'
description: 「」の「クォンタムプログラムの概要」#
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233977"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="b9867-103">Q # クォンタムプログラミング言語</span><span class="sxs-lookup"><span data-stu-id="b9867-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="b9867-104">Q # プログラミング言語について理解しておく必要があるものはすべて、 [q # 言語ガイド](xref:microsoft.quantum.qsharp.index)で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="b9867-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="b9867-105">他の [言語の設計プロセス](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) と同様に、microsoft はオープンソースであり、投稿を歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="b9867-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="b9867-106">Q # の背後にある基礎と動機の背景については、「 [q # が必要な理由](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9867-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="b9867-107">Q # は、簡単な概要については、「Quantum Development Kit (QDK)」の一部として出荷されています。 [QDK](xref:microsoft.quantum.overview.q-sharp)の概要については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b9867-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="b9867-108">クォンタムプログラムとは</span><span class="sxs-lookup"><span data-stu-id="b9867-108">What is a quantum program?</span></span>

<span data-ttu-id="b9867-109">クォンタムプログラムは、クォンタムシステムと対話することによって計算を実行する、特定の一連の従来のサブルーチンとして表示されます。Q # で記述されたプログラムは、クォンタム状態を直接モデル化するのではなく、従来のコントロールコンピューターが qubits とどのようにやり取りするかを説明します。</span><span class="sxs-lookup"><span data-stu-id="b9867-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="b9867-110">これにより、各ターゲットコンピューター上でもクォンタムの状態を完全には認識できなくなります。これは、コンピューターによって *は* 、解釈が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9867-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="b9867-111">重要なのは、Q # では、量子機構の qubit またはその他のプロパティの状態を直接 introspect ことができないことです。これにより、実際には、1つのコンピューターで Q # プログラムが物理的に実行されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="b9867-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="b9867-112">代わりに、プログラムはなどの操作を呼び出して、 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) qubit から古典情報を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="b9867-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="b9867-113">割り当てられた後、qubit を操作や関数に渡すことができます。 *呼び出し* 可能とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b9867-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="b9867-114">これは、Q # プログラムが qubit を使用して実行できることです。Qubit の状態に対する直接的なアクションはすべて、やなどの *組み込み* 呼び出しが定義されてい [`X`](xref:Microsoft.Quantum.Intrinsic.X) ます。これは、その [`H`](xref:Microsoft.Quantum.Intrinsic.H) 実装が Q # で定義されておらず、ターゲットコンピューターによって定義されているものであるためです。</span><span class="sxs-lookup"><span data-stu-id="b9867-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="b9867-115">これらの操作は *、実際には、* 特定の q&a プログラムを実行するために使用するターゲットコンピューターによってのみ具体的に行われます。</span><span class="sxs-lookup"><span data-stu-id="b9867-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="b9867-116">たとえば、 [フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でプログラムを実行すると、シミュレーターはシミュレートされたクォンタムシステムに対応する数学的操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b9867-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="b9867-117">しかし、将来的に見てみると、ターゲットコンピューターが実際の quantum のコンピューターである場合、Q # でこのような操作を呼び出すと、*実際* のクォンタムシステムに対応する *実際* の操作を実行するように、クォンタムコンピューターが指示されます (正確に時間がかかるレーザーパルスなど)。</span><span class="sxs-lookup"><span data-stu-id="b9867-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="b9867-118">Q # プログラムは、ターゲットコンピューターによって定義されたこれらの操作を結合して、クォンタム計算を表す新しい高レベルの操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="b9867-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="b9867-119">このように Q # を使用すると、対象のマシンまたはシミュレーターの構造に関しても一般的に、基になるクォンタムやハイブリッドクォンタム–クラシックアルゴリズムを簡単に表現できます。</span><span class="sxs-lookup"><span data-stu-id="b9867-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="b9867-120">単純な例として、$ \ket $ 状態に1つの qubit を割り当てて {0} から、Hadamard 操作を適用 `H` して結果を基に測定する次のプログラムがあり `PauliZ` ます。</span><span class="sxs-lookup"><span data-stu-id="b9867-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="b9867-121">Quantum [Katas](https://github.com/microsoft/QuantumKatas#introduction) は、一般的なクォンタム操作や qubits の操作方法など、 [クォンタムコンピューティングの概念](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) についての優れた概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9867-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="b9867-122">その他の例につい [ては、「組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9867-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



