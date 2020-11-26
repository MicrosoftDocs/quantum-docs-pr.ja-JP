---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 275f31ea636d15eb0d78e5148e8af6b58d22729d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209657"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="19fce-102">ApplyCCNOTChain 操作</span><span class="sxs-lookup"><span data-stu-id="19fce-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="19fce-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19fce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19fce-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19fce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19fce-105">2つの qubit レジスタの対応するビットで制御される CCNOT ゲートのカスケードを実装します。これは、いずれかのレジスタの次の qubit で動作します。</span><span class="sxs-lookup"><span data-stu-id="19fce-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="19fce-106">両方のレジスタでコントロールとして位置0にある qubits から、CCNOT はターゲットレジスタの位置1にある qubits に適用され、ターゲットレジスタの位置2の qubits に作用する位置1の qubits によって制御されます。その後、ターゲットの qubits に対するアクションで終了 `Length(nQubits)-1` します。</span><span class="sxs-lookup"><span data-stu-id="19fce-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="19fce-107">入力</span><span class="sxs-lookup"><span data-stu-id="19fce-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="19fce-108">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19fce-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19fce-109">Qubit レジスタ。コントロールにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="19fce-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="19fce-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19fce-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19fce-111">Qubit レジスタ。コントロールとターゲットとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="19fce-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19fce-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19fce-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="19fce-113">解説</span><span class="sxs-lookup"><span data-stu-id="19fce-113">Remarks</span></span>

<span data-ttu-id="19fce-114">ターゲットの qubit レジスタには、もう一方のレジスタよりも1つの qubit が必要です。</span><span class="sxs-lookup"><span data-stu-id="19fce-114">The target qubit register must have one qubit more than the other register.</span></span>