---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219143"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="89a56-102">ApplyCNOTChain 操作</span><span class="sxs-lookup"><span data-stu-id="89a56-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="89a56-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89a56-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89a56-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89a56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89a56-105">Qubits のレジスタのパリティを計算します。</span><span class="sxs-lookup"><span data-stu-id="89a56-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="89a56-106">説明</span><span class="sxs-lookup"><span data-stu-id="89a56-106">Description</span></span>

<span data-ttu-id="89a56-107">この操作では、入力の状態を $ $ \begin{align} \ket{q_0} \ket{q_1} \ cドット \ket{q_ {n-1}} & \ map\ket{q_0} \ket{q_0 \ oplus q_1} \ket{q_0/oplus q_1 \ oplus q_2} \ cドット \ket{q_0 \ oplus/cドット/oplus q_ {n-1}} として変換します。</span><span class="sxs-lookup"><span data-stu-id="89a56-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="89a56-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="89a56-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="89a56-109">入力</span><span class="sxs-lookup"><span data-stu-id="89a56-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="89a56-110">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="89a56-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="89a56-111">パリティを計算および格納する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="89a56-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89a56-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89a56-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

