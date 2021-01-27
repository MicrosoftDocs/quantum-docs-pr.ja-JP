---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850535"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="6a0ec-102">ApplyToPartition 操作</span><span class="sxs-lookup"><span data-stu-id="6a0ec-102">ApplyToPartition operation</span></span>

<span data-ttu-id="6a0ec-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a0ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a0ec-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a0ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a0ec-105">レジスタの特定のパーティションに2つの操作を適用して、2つの部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6a0ec-106">入力</span><span class="sxs-lookup"><span data-stu-id="6a0ec-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="6a0ec-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a0ec-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6a0ec-108">指定されたパーティションに適用される操作のペア。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="6a0ec-109">numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a0ec-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a0ec-110">パーティションの最初の部分に入れるターゲットからの qubits の数。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="6a0ec-111">残りの qubits は、パーティションの2番目の部分を構成します。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6a0ec-112">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6a0ec-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6a0ec-113">指定された2つの操作によってパーティション分割および操作されている qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="6a0ec-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a0ec-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a0ec-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6a0ec-115">参照</span><span class="sxs-lookup"><span data-stu-id="6a0ec-115">See Also</span></span>

- [<span data-ttu-id="6a0ec-116">Microsoft. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="6a0ec-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="6a0ec-117">Microsoft. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="6a0ec-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="6a0ec-118">Microsoft. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="6a0ec-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)