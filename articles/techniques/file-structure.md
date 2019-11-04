---
title: Quantum 開発手法の概要 |Microsoft Docs
description: クォンタム開発手法の概要
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442569"
---
# <a name="q-program-overview"></a><span data-ttu-id="1d1cf-103">Q # プログラムの概要</span><span class="sxs-lookup"><span data-stu-id="1d1cf-103">Q# program overview</span></span>

<span data-ttu-id="1d1cf-104">Q # は、クォンタムコンピューティング用のスケーラブルでマルチパラダイムのドメイン固有のプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-104">Q# is a scalable, multi-paradigm, domain-specific programming language for quantum computing.</span></span> <span data-ttu-id="1d1cf-105">Q # は、クォンタムコンピューターで命令を実行する方法を説明するために使用できるクォンタムプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-105">Q# is a quantum programming language in that it can be used to describe how instructions are executed on quantum machines.</span></span> <span data-ttu-id="1d1cf-106">対象となる可能性のあるマシンは、シミュレーターから実際の量子ハードウェアまで多岐に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-106">The machines that can be targeted range from simulators to actual quantum hardware.</span></span> <span data-ttu-id="1d1cf-107">Q # はスケーラブルです。これを使用すると、いくつかの qubits で実行されるテレポートなどの単純なデモンストレーションプログラムを作成できます。また、数百万の qubits を持つ大規模なコンピューターを必要とする複雑な分子のシミュレーションなど、大規模な高度なプログラムの作成もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-107">Q# is scalable: it can be used to write simple demonstration programs like teleport that run on a few qubits, but also supports writing large, sophisticated programs such as simulations of complex molecules that will require large machines with millions of qubits.</span></span> <span data-ttu-id="1d1cf-108">大規模な物理マシンが今後も使用されている場合でも、Q # ではプログラマが複雑なクォンタムアルゴリズムをプログラミングできます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-108">Even though large physical machines are still in the future, Q# allows a programmer to program complex quantum algorithms now.</span></span> <span data-ttu-id="1d1cf-109">さらに、Q # は、デバッグ、プロファイリング、リソースの推定、特定の特別な目的のシミュレーションなどのさまざまなタスクをスケーラブルな方法でサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-109">What is more, Q# supports various tasks such as debugging, profiling, resource estimation, and certain special-purpose simulations in a scalable way.</span></span> 

<span data-ttu-id="1d1cf-110">技術的な観点からは、クォンタムプログラムは特定の一連のクラシック関数として認識されます。これを呼び出すと、その副作用としてクォンタム回線が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-110">From a technical perspective, a quantum program can be seen as a particular set of classical functions which, when called, generate quantum circuits as their side effects.</span></span> <span data-ttu-id="1d1cf-111">このビューの重要な結果として、Q # で記述されたプログラムは、qubits 自体を直接モデル化するのではなく、従来のコントロールコンピューターがその qubits とどのようにやり取りするかを説明します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-111">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="1d1cf-112">仕様により、Q # はクォンタムの状態やその他の量子機構のプロパティを直接定義するのではなく、言語で定義されたさまざまなサブルーチンのアクションを通じて間接的に実行します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-112">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly, but rather does so indirectly through the action of the various subroutines defined in the language.</span></span>
<span data-ttu-id="1d1cf-113">たとえば、「[クォンタムコンピューティングの概念](xref:microsoft.quantum.concepts.intro)」ガイドで説明されているように、"$ \ket{+} = \ left (\ket{0} + \ket{1}]/\ sqrt{2}$" という状態を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-113">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="1d1cf-114">この状態を Q # で準備するには、qubits が $ \ket{0}$ state で初期化され、$ \ket{+} = H\ket{0}$ というファクトを使用します。ここで、$H $ は Hadamard transform です。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-114">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a><span data-ttu-id="1d1cf-115">Q # 変換クォンタムの状態</span><span class="sxs-lookup"><span data-stu-id="1d1cf-115">Q# tranformations of quantum states</span></span>

<span data-ttu-id="1d1cf-116">重要なのは、上記のプログラムを作成するときに、Q # 内の状態を明示的に参照するのではなく、その状態がプログラムによってどのように*変換*されたかを説明することです。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-116">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="1d1cf-117">したがって、グラフィックスシェーダープログラムが各頂点への変換の説明を累積するのと同様に、Q # のクォンタムプログラムはクォンタムの状態への変換を累積します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-117">Thus, similar to how a graphics shader program accumulates a description of transformations to each vertex, a quantum program in Q# accumulates transformations to quantum states.</span></span>
<span data-ttu-id="1d1cf-118">これにより、各ターゲットコンピューター上でもクォンタムの状態を完全には認識できなくなります。これは、コンピューターによって*は*、解釈が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-118">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="1d1cf-119">Q # プログラムの観点から見ると、qubit はターゲットコンピューターの内部構造への完全に不透明な参照です。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-119">From the perspective of a Q# program, a qubit is an entirely opaque reference to the internal structure of a target machine.</span></span>
<span data-ttu-id="1d1cf-120">Q # プログラムは、introspect の状態、ターゲットコンピューター上の表現、またはプログラムで使用可能な他の qubit と同じ qubit であるかどうかを確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-120">A Q# program has no ability to introspect into the state of a qubit, its representation on a target machine, or even whether it is the same qubit as any other qubit available to the program.</span></span>
<span data-ttu-id="1d1cf-121">代わりに、プログラムは、`Measure` などの操作を呼び出して、qubit から情報を取得し、`X` や `H` などの操作を呼び出して、qubit の状態を操作できます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-121">Rather, a program can call operations such as `Measure` to learn information from a qubit, and call operations such as `X` and `H` to act on the state of a qubit.</span></span>
<span data-ttu-id="1d1cf-122">これらの操作には、言語内に組み込みの定義がないため、特定の Q # プログラムを実行するために使用されるターゲットコンピューターによってのみ具体的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-122">These operations have no intrinsic definition within the language, and are made concrete only by the target machine used to run a particular Q# program.</span></span>
<span data-ttu-id="1d1cf-123">Q # プログラムは、ターゲットコンピューターによって定義されたこれらの操作を結合して、クォンタム計算を表す新しい高レベルの操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-123">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="1d1cf-124">このようにして、Q # を使用すると、ターゲットコンピューターまたはシミュレーターの構造に関しても一般的に、基になるクォンタムやハイブリッド量子化アルゴリズムを簡単に表現できます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-124">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum-classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="1d1cf-125">Q # 操作と関数</span><span class="sxs-lookup"><span data-stu-id="1d1cf-125">Q# operations and functions</span></span>

<span data-ttu-id="1d1cf-126">具体的に Q # プログラムは、1つ以上の*操作*、1つ以上の*関数*、およびユーザー定義型で構成されています。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-126">Concretely, a Q# program is comprised of one or more *operations*, one or more *functions*, and user defined types.</span></span> <span data-ttu-id="1d1cf-127">操作は、クォンタムコンピューターの状態の変換を記述するために使用され、Q # プログラムの最も基本的なビルドブロックです。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-127">Operations are used to describe the transformations of the state of a quantum machine and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="1d1cf-128">Q # で定義された各操作は、ターゲットコンピューターによって実装されている*組み込みの組み込み操作を*含む、他の任意の数の操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-128">Each operation defined in Q# may then call any number of other operations, including the built-in *intrinsic* operations implemented by a target machine.</span></span>
<span data-ttu-id="1d1cf-129">コンパイルされると、各操作はターゲットコンピューターに提供できる .NET クラス型として表されます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-129">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="1d1cf-130">操作とは対照的に、関数は純粋な古典動作を説明するために使用されます。また、古典出力値の計算以外にも影響はありません。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-130">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span> <span data-ttu-id="1d1cf-131">Q # は、厳密に型指定された言語であり、組み込みのプリミティブ型のセットと、ユーザー定義型のサポートを備えています。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-131">Q# is a strongly typed language and comes with a set of built-in primitive types as well as support for user defined types.</span></span> 

<span data-ttu-id="1d1cf-132">このガイドの残りの部分では、さまざまな言語の概念と構成要素を使用して、操作、関数、および型の基本的な構成要素を使用して複雑なクォンタムプログラムを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-132">Throughout the rest of this guide, we will see how to use different language concepts and constructs to help us define complex quantum programs through the basic building blocks of operations, functions, and types.</span></span> 

## <a name="structure-of-q-source-files"></a><span data-ttu-id="1d1cf-133">Q # ソースファイルの構造</span><span class="sxs-lookup"><span data-stu-id="1d1cf-133">Structure of Q# Source Files</span></span>

<span data-ttu-id="1d1cf-134">少なくとも、Q # ソースファイルは*名前空間宣言*で構成されます。これは、ソースファイル内の定義を格納する .net 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-134">Minimally, a Q# source file consists of a *namespace declaration*, which specifies a .NET namespace which will contain the definitions in the source file.</span></span>
<span data-ttu-id="1d1cf-135">他の Q # ソースファイルおよびライブラリの定義は、`open` ステートメントを使用して含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-135">Definitions from other Q# source files and libraries can be included using the `open` statement.</span></span>
<span data-ttu-id="1d1cf-136">たとえば、基本的なゲートを定義する操作のほとんどは、<xref:microsoft.quantum.intrinsic> 名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-136">For instance, most of the operations defining fundamental gates are defined in the <xref:microsoft.quantum.intrinsic> namespace.</span></span>
<span data-ttu-id="1d1cf-137">コードでこれを使用できるようにするには、各ファイルの先頭にその名前空間を `open` します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-137">To make this available to our code, we simply `open` that namespace at the top of each file:</span></span>

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

<span data-ttu-id="1d1cf-138">名前空間内では、各 Q # ソースファイルで、*操作*、*関数*、および*ユーザー定義型*の任意の組み合わせを定義できます。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-138">Within a namespace, each Q# source file can define any combination of *operations*, *functions*, and *user-defined types*.</span></span>
<span data-ttu-id="1d1cf-139">このセクションの残りの部分では、それぞれについて説明し、効果的なクォンタムプログラムを作成するために実際に使用する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d1cf-139">In the rest of this section, we will describe each in turn and provide examples of how they can be used in practice to make useful quantum programs.</span></span>
