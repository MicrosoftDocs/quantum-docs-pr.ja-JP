---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715514"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="a30e1-102">RestrictedToSubregisterC 関数</span><span class="sxs-lookup"><span data-stu-id="a30e1-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="a30e1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a30e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a30e1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a30e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a30e1-105">操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。</span><span class="sxs-lookup"><span data-stu-id="a30e1-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="a30e1-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="a30e1-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a30e1-107">入力</span><span class="sxs-lookup"><span data-stu-id="a30e1-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="a30e1-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="a30e1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a30e1-109">サブレジスタに限定される操作。</span><span class="sxs-lookup"><span data-stu-id="a30e1-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="a30e1-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a30e1-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a30e1-111">インデックスの配列。操作が制限される qubits を示します。</span><span class="sxs-lookup"><span data-stu-id="a30e1-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-ctl"></a><span data-ttu-id="a30e1-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="a30e1-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="a30e1-113">参照</span><span class="sxs-lookup"><span data-stu-id="a30e1-113">See Also</span></span>

- [<span data-ttu-id="a30e1-114">Microsoft. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="a30e1-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)