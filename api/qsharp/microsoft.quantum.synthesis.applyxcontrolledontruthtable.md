---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203299"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="d436b-102">ApplyXControlledOnTruthTable 操作</span><span class="sxs-lookup"><span data-stu-id="d436b-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="d436b-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d436b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d436b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d436b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d436b-105">の @"microsoft.quantum.intrinsic.x" `target` クラシック代入に対してブール関数が true と評価された場合に、操作をに適用し `func` `controlRegister` ます。</span><span class="sxs-lookup"><span data-stu-id="d436b-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d436b-106">説明</span><span class="sxs-lookup"><span data-stu-id="d436b-106">Description</span></span>

<span data-ttu-id="d436b-107">この操作は、\begin{align} U\ket {x} \ k {y} = \ket{x}\ket{y/oplus f (x)} \end{align} を実装します。ここで $x $ と $y $ `controlRegister` `target` はそれぞれとを表します。</span><span class="sxs-lookup"><span data-stu-id="d436b-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="d436b-108">ブール関数 $f $ は、大規模な整数の観点から真理値テーブルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="d436b-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="d436b-109">たとえば、3つの入力に対するマジョリティ関数は bitstring によって表されます。この場合、 `11101000` 最上位ビットは `1` 入力割り当てに相当し、最下位 `(1, 1, 1)` ビットは `0` 入力割り当てに相当し `(0, 0, 0)` ます。</span><span class="sxs-lookup"><span data-stu-id="d436b-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="d436b-110">これは、 `0xE8L` 16 進数表記では、または10進表記のように、大きい整数で表すことができ `232L` ます。</span><span class="sxs-lookup"><span data-stu-id="d436b-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="d436b-111">サフィックスは、 `L` 定数が型であることを示し `BigInt` ます。</span><span class="sxs-lookup"><span data-stu-id="d436b-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="d436b-112">この表現の詳細については、 [真理テーブル kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="d436b-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="d436b-113">実装では @"microsoft.quantum.intrinsic.cnot" 、およびゲートを使用し @"microsoft.quantum.intrinsic.r1" ます。</span><span class="sxs-lookup"><span data-stu-id="d436b-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="d436b-114">入力</span><span class="sxs-lookup"><span data-stu-id="d436b-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="d436b-115">func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d436b-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d436b-116">ブール型の真理値テーブルを大きな整数として表現</span><span class="sxs-lookup"><span data-stu-id="d436b-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="d436b-117">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d436b-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d436b-118">制御 qubits の登録</span><span class="sxs-lookup"><span data-stu-id="d436b-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d436b-119">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d436b-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d436b-120">ターゲット qubit</span><span class="sxs-lookup"><span data-stu-id="d436b-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="d436b-121">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d436b-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d436b-122">リファレンス</span><span class="sxs-lookup"><span data-stu-id="d436b-122">References</span></span>

- [<span data-ttu-id="d436b-123">*Schuch*、 *Siewert*、prl 91、no. 027902、2003、arxiv: quant-ph/0303063</span><span class="sxs-lookup"><span data-stu-id="d436b-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="d436b-124">*Mathias Soeken*, *Martin Roetteler*, arxiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="d436b-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="d436b-125">参照</span><span class="sxs-lookup"><span data-stu-id="d436b-125">See Also</span></span>

- [<span data-ttu-id="d436b-126">ApplyXControlledOnTruthTableWithCleanTarget です。</span><span class="sxs-lookup"><span data-stu-id="d436b-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)