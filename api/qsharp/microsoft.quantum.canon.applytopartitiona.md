---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: f8f773e9fc3c18467185f9717a235649be8b385a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841304"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="08a2f-102">ApplyToPartitionA 操作</span><span class="sxs-lookup"><span data-stu-id="08a2f-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="08a2f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="08a2f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="08a2f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08a2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08a2f-105">レジスタの特定のパーティションに2つの操作を適用して、2つの部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="08a2f-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="08a2f-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="08a2f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="08a2f-107">入力</span><span class="sxs-lookup"><span data-stu-id="08a2f-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="08a2f-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞</span><span class="sxs-lookup"><span data-stu-id="08a2f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="08a2f-109">指定されたパーティションに適用される操作のペア。</span><span class="sxs-lookup"><span data-stu-id="08a2f-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="08a2f-110">numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="08a2f-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="08a2f-111">パーティションの最初の部分に入れるターゲットからの qubits の数。</span><span class="sxs-lookup"><span data-stu-id="08a2f-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="08a2f-112">残りの qubits は、パーティションの2番目の部分を構成します。</span><span class="sxs-lookup"><span data-stu-id="08a2f-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="08a2f-113">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="08a2f-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="08a2f-114">指定された2つの操作によってパーティション分割および操作されている qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="08a2f-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="08a2f-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08a2f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="08a2f-116">参照</span><span class="sxs-lookup"><span data-stu-id="08a2f-116">See Also</span></span>

- [<span data-ttu-id="08a2f-117">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="08a2f-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)