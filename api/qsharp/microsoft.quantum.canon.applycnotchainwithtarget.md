---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718363"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="3a1ce-102">ApplyCNOTChainWithTarget 操作</span><span class="sxs-lookup"><span data-stu-id="3a1ce-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="3a1ce-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a1ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a1ce-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a1ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a1ce-105">Qubits の配列のパリティをターゲットの qubits に計算します。</span><span class="sxs-lookup"><span data-stu-id="3a1ce-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="3a1ce-106">説明</span><span class="sxs-lookup"><span data-stu-id="3a1ce-106">Description</span></span>

<span data-ttu-id="3a1ce-107">配列の初期状態が $ \ket{q_0} \ket{q_1} \ket{の場合は q_ {\ text{target{1}} $, 最終的な状態は、$ \ket{q_0} \ket{q_1 \ oplus q_0} \ cドット \ket{q_ {n-1} \ oplus/cドット \ oplus q_0 {/text{target{1}} $ によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ce-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="3a1ce-108">入力</span><span class="sxs-lookup"><span data-stu-id="3a1ce-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="3a1ce-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3a1ce-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3a1ce-110">パリティが計算される qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="3a1ce-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="3a1ce-111">targetQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3a1ce-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3a1ce-112">' Qubit ' のパリティが Xor される最後の qubit。</span><span class="sxs-lookup"><span data-stu-id="3a1ce-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a1ce-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a1ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3a1ce-114">解説</span><span class="sxs-lookup"><span data-stu-id="3a1ce-114">Remarks</span></span>

<span data-ttu-id="3a1ce-115">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a1ce-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="3a1ce-116">および</span><span class="sxs-lookup"><span data-stu-id="3a1ce-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```