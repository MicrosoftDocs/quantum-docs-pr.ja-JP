---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 36010ba667190c237b64f60b7246010199a8ba1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717969"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="45df2-102">ApplyMultiControlledC 操作</span><span class="sxs-lookup"><span data-stu-id="45df2-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="45df2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45df2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45df2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45df2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45df2-105">1つの操作の制御された複数のバージョンを適用します。</span><span class="sxs-lookup"><span data-stu-id="45df2-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="45df2-106">修飾子は、 `C` single qubit 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="45df2-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="45df2-107">入力</span><span class="sxs-lookup"><span data-stu-id="45df2-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="45df2-108">Sing(Controlledop): [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45df2-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="45df2-109">1つの qubit で制御される操作。</span><span class="sxs-lookup"><span data-stu-id="45df2-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="45df2-110">操作の引数の最初の qubit はコントロールであると見なされ、残りはターゲット qubit と見なされます。</span><span class="sxs-lookup"><span data-stu-id="45df2-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="45df2-111">`ApplyMultiControlled` は常に `singlyControlledOp` 、長さが1以上の引数を使用してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45df2-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="45df2-112">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="45df2-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="45df2-113">構築に使用する制御制御された非対応のゲート。</span><span class="sxs-lookup"><span data-stu-id="45df2-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="45df2-114">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45df2-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45df2-115">`singlyControlledOp`で制御される qubits。</span><span class="sxs-lookup"><span data-stu-id="45df2-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="45df2-116">の長さは `controls` 1 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="45df2-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="45df2-117">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45df2-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45df2-118">に対して動作するターゲットの qubits `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="45df2-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45df2-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45df2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45df2-120">解説</span><span class="sxs-lookup"><span data-stu-id="45df2-120">Remarks</span></span>

<span data-ttu-id="45df2-121">この操作では、clean ancilla qubits のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="45df2-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="45df2-122">説明とサーキットの図については、図4.10 のセクション4.3 を参照してください & 語</span><span class="sxs-lookup"><span data-stu-id="45df2-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="45df2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="45df2-123">References</span></span>

- [<span data-ttu-id="45df2-124">*Michael、Isaac、語* 、量子計算、およびクォンタム情報</span><span class="sxs-lookup"><span data-stu-id="45df2-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="45df2-125">参照</span><span class="sxs-lookup"><span data-stu-id="45df2-125">See Also</span></span>

- [<span data-ttu-id="45df2-126">Microsoft. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="45df2-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)