---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715542"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="75784-102">RestrictedToSubregister 関数</span><span class="sxs-lookup"><span data-stu-id="75784-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="75784-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75784-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75784-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75784-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75784-105">操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。</span><span class="sxs-lookup"><span data-stu-id="75784-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="75784-106">入力</span><span class="sxs-lookup"><span data-stu-id="75784-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="75784-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75784-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="75784-108">サブレジスタに限定される操作。</span><span class="sxs-lookup"><span data-stu-id="75784-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="75784-109">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="75784-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="75784-110">インデックスの配列。操作が制限される qubits を示します。</span><span class="sxs-lookup"><span data-stu-id="75784-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="75784-111">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75784-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="75784-112">参照</span><span class="sxs-lookup"><span data-stu-id="75784-112">See Also</span></span>

- [<span data-ttu-id="75784-113">Microsoft. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="75784-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="75784-114">Microsoft. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="75784-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="75784-115">Microsoft. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="75784-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)