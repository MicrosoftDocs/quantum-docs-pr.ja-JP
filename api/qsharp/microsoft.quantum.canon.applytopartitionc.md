---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 43cf43fa2bf9c00a4096b39555b8f6080dd506d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850522"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="fef5c-102">ApplyToPartitionC 操作</span><span class="sxs-lookup"><span data-stu-id="fef5c-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="fef5c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fef5c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fef5c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fef5c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fef5c-105">レジスタの特定のパーティションに2つの操作を適用して、2つの部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="fef5c-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="fef5c-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="fef5c-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="fef5c-107">入力</span><span class="sxs-lookup"><span data-stu-id="fef5c-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="fef5c-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl</span><span class="sxs-lookup"><span data-stu-id="fef5c-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fef5c-109">指定されたパーティションに適用される操作のペア。</span><span class="sxs-lookup"><span data-stu-id="fef5c-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="fef5c-110">numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fef5c-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fef5c-111">パーティションの最初の部分に入れるターゲットからの qubits の数。</span><span class="sxs-lookup"><span data-stu-id="fef5c-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="fef5c-112">残りの qubits は、パーティションの2番目の部分を構成します。</span><span class="sxs-lookup"><span data-stu-id="fef5c-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fef5c-113">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fef5c-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fef5c-114">指定された2つの操作によってパーティション分割および操作されている qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="fef5c-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fef5c-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fef5c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fef5c-116">参照</span><span class="sxs-lookup"><span data-stu-id="fef5c-116">See Also</span></span>

- [<span data-ttu-id="fef5c-117">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="fef5c-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)