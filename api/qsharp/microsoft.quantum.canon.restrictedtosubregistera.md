---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715533"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="475d5-102">RestrictedToSubregisterA 関数</span><span class="sxs-lookup"><span data-stu-id="475d5-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="475d5-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="475d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="475d5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="475d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="475d5-105">操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。</span><span class="sxs-lookup"><span data-stu-id="475d5-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="475d5-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="475d5-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="475d5-107">入力</span><span class="sxs-lookup"><span data-stu-id="475d5-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="475d5-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="475d5-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="475d5-109">サブレジスタに限定される操作。</span><span class="sxs-lookup"><span data-stu-id="475d5-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="475d5-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="475d5-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="475d5-111">インデックスの配列。操作が制限される qubits を示します。</span><span class="sxs-lookup"><span data-stu-id="475d5-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj"></a><span data-ttu-id="475d5-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="475d5-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="475d5-113">参照</span><span class="sxs-lookup"><span data-stu-id="475d5-113">See Also</span></span>

- [<span data-ttu-id="475d5-114">Microsoft. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="475d5-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)