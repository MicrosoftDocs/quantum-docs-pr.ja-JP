---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845114"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="42d3f-102">ApplyCNOTChainWithTarget 操作</span><span class="sxs-lookup"><span data-stu-id="42d3f-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="42d3f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42d3f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42d3f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42d3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42d3f-105">Qubits の配列のパリティをターゲットの qubits に計算します。</span><span class="sxs-lookup"><span data-stu-id="42d3f-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="42d3f-106">説明</span><span class="sxs-lookup"><span data-stu-id="42d3f-106">Description</span></span>

<span data-ttu-id="42d3f-107">配列の初期状態が $ \ket{q_0} \ket{q_1} \ket{の場合は q_ {\ text{target{1}} $, 最終的な状態は、$ \ket{q_0} \ket{q_1 \ oplus q_0} \ cドット \ket{q_ {n-1} \ oplus/cドット \ oplus q_0 {/text{target{1}} $ によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="42d3f-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="42d3f-108">入力</span><span class="sxs-lookup"><span data-stu-id="42d3f-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="42d3f-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42d3f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42d3f-110">パリティが計算される qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="42d3f-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="42d3f-111">targetQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42d3f-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42d3f-112">' Qubit ' のパリティが Xor される最後の qubit。</span><span class="sxs-lookup"><span data-stu-id="42d3f-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42d3f-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42d3f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="42d3f-114">解説</span><span class="sxs-lookup"><span data-stu-id="42d3f-114">Remarks</span></span>

<span data-ttu-id="42d3f-115">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="42d3f-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="42d3f-116">and</span><span class="sxs-lookup"><span data-stu-id="42d3f-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```