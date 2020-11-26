---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208110"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="b4577-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="b4577-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="b4577-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b4577-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b4577-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4577-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4577-105">インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="b4577-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b4577-106">入力</span><span class="sxs-lookup"><span data-stu-id="b4577-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="b4577-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4577-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b4577-108">Subregister に適用する操作です。</span><span class="sxs-lookup"><span data-stu-id="b4577-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="b4577-109">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b4577-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b4577-110">操作が適用される qubits を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="b4577-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b4577-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b4577-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b4577-112">操作が動作する登録です。</span><span class="sxs-lookup"><span data-stu-id="b4577-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4577-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4577-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b4577-114">参照</span><span class="sxs-lookup"><span data-stu-id="b4577-114">See Also</span></span>

- [<span data-ttu-id="b4577-115">Microsoft. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="b4577-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="b4577-116">Microsoft. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="b4577-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="b4577-117">Microsoft. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="b4577-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)