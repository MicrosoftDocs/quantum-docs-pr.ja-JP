---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: RestrictedToSubregisterCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715528"
---
# <a name="restrictedtosubregisterca-function"></a><span data-ttu-id="c9313-102">RestrictedToSubregisterCA 関数</span><span class="sxs-lookup"><span data-stu-id="c9313-102">RestrictedToSubregisterCA function</span></span>

<span data-ttu-id="c9313-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9313-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9313-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9313-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9313-105">操作をレジスタのインデックスの配列 (サブレジスタ) に制限します。</span><span class="sxs-lookup"><span data-stu-id="c9313-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="c9313-106">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c9313-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c9313-107">入力</span><span class="sxs-lookup"><span data-stu-id="c9313-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="c9313-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c9313-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c9313-109">サブレジスタに限定される操作。</span><span class="sxs-lookup"><span data-stu-id="c9313-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="c9313-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c9313-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c9313-111">インデックスの配列。操作が制限される qubits を示します。</span><span class="sxs-lookup"><span data-stu-id="c9313-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="c9313-112">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c9313-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="c9313-113">参照</span><span class="sxs-lookup"><span data-stu-id="c9313-113">See Also</span></span>

- [<span data-ttu-id="c9313-114">Microsoft. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="c9313-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)