---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2a2eb7ee5b437ec5fb633bfb4bdccd0cb1d253ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208025"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="74eb9-102">ApplyToSubregisterC 操作</span><span class="sxs-lookup"><span data-stu-id="74eb9-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="74eb9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74eb9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74eb9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74eb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74eb9-105">インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="74eb9-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="74eb9-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="74eb9-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="74eb9-107">入力</span><span class="sxs-lookup"><span data-stu-id="74eb9-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="74eb9-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl</span><span class="sxs-lookup"><span data-stu-id="74eb9-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="74eb9-109">Subregister に適用する操作です。</span><span class="sxs-lookup"><span data-stu-id="74eb9-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="74eb9-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74eb9-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="74eb9-111">操作が適用される qubits を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="74eb9-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="74eb9-112">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="74eb9-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="74eb9-113">操作が動作する登録です。</span><span class="sxs-lookup"><span data-stu-id="74eb9-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74eb9-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74eb9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="74eb9-115">参照</span><span class="sxs-lookup"><span data-stu-id="74eb9-115">See Also</span></span>

- [<span data-ttu-id="74eb9-116">Microsoft. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="74eb9-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)