---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: edea0e565984cffb13b146cb336f90762f647636
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208059"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="5264d-102">ApplyToSubregisterA 操作</span><span class="sxs-lookup"><span data-stu-id="5264d-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="5264d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5264d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5264d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5264d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5264d-105">インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="5264d-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="5264d-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="5264d-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5264d-107">入力</span><span class="sxs-lookup"><span data-stu-id="5264d-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="5264d-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="5264d-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5264d-109">Subregister に適用する操作です。</span><span class="sxs-lookup"><span data-stu-id="5264d-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="5264d-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5264d-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5264d-111">操作が適用される qubits を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="5264d-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5264d-112">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5264d-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5264d-113">操作が動作する登録です。</span><span class="sxs-lookup"><span data-stu-id="5264d-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5264d-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5264d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5264d-115">参照</span><span class="sxs-lookup"><span data-stu-id="5264d-115">See Also</span></span>

- [<span data-ttu-id="5264d-116">Microsoft. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="5264d-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)