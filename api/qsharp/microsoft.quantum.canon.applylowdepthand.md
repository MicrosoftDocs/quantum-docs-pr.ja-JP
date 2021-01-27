---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841707"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="f5cca-102">ApplyLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="f5cca-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="f5cca-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5cca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5cca-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5cca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5cca-105">指定されたターゲットの qubit が、両方のコントロール qubit が1状態 (T 深度 1) である場合にのみ、測定を使用して adjoint 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5cca-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f5cca-106">説明</span><span class="sxs-lookup"><span data-stu-id="f5cca-106">Description</span></span>

<span data-ttu-id="f5cca-107">`target`両方のコントロールが1で、 `target` が状態が0であると想定している場合にのみ、を反転させます。</span><span class="sxs-lookup"><span data-stu-id="f5cca-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="f5cca-108">この操作には、T カウント4、T 深度1があり、1つのヘルパー qubit が必要です。このため、が0であることがわかっている場合は、CCNOT 操作に適している可能性があり `target` ます。</span><span class="sxs-lookup"><span data-stu-id="f5cca-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="f5cca-109">この操作の adjoint は測定ベースであり、T ゲートを必要とせず、ヘルパー qubit も必要としません。</span><span class="sxs-lookup"><span data-stu-id="f5cca-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="f5cca-110">入力</span><span class="sxs-lookup"><span data-stu-id="f5cca-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="f5cca-111">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5cca-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5cca-112">最初のコントロールの qubit</span><span class="sxs-lookup"><span data-stu-id="f5cca-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="f5cca-113">control2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5cca-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5cca-114">2番目のコントロール qubit</span><span class="sxs-lookup"><span data-stu-id="f5cca-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f5cca-115">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5cca-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5cca-116">ターゲット補助 qubit;状態は0である必要があります</span><span class="sxs-lookup"><span data-stu-id="f5cca-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5cca-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5cca-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f5cca-118">References</span><span class="sxs-lookup"><span data-stu-id="f5cca-118">References</span></span>

- <span data-ttu-id="f5cca-119">Cody Jones: 「fault トレラントな Toffoli ゲートのための斬新構造」、「Phys 87、022328、2013 [Arxiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA</span><span class="sxs-lookup"><span data-stu-id="f5cca-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="f5cca-120">Peter Selinger: "T 深度 one のクォンタム回線"、Phys 87、042302、2013 [Arxiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA 87.042302</span><span class="sxs-lookup"><span data-stu-id="f5cca-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>