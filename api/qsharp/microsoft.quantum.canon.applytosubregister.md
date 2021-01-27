---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850483"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="73ab8-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="73ab8-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="73ab8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73ab8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73ab8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73ab8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73ab8-105">インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="73ab8-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="73ab8-106">入力</span><span class="sxs-lookup"><span data-stu-id="73ab8-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="73ab8-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73ab8-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="73ab8-108">Subregister に適用する操作です。</span><span class="sxs-lookup"><span data-stu-id="73ab8-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="73ab8-109">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73ab8-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="73ab8-110">操作が適用される qubits を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="73ab8-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="73ab8-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73ab8-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73ab8-112">操作が動作する登録です。</span><span class="sxs-lookup"><span data-stu-id="73ab8-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73ab8-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73ab8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="73ab8-114">例</span><span class="sxs-lookup"><span data-stu-id="73ab8-114">Example</span></span>

<span data-ttu-id="73ab8-115">次の3つの qubit 状態を作成します。 $ \ frac {1} {\ sqrt {2} } \ket {0} \_ 2 (\ket {0} \_ 1 \ k ( {0} 3 + \ket {1} \_ 1 \ k {1} ) $:</span><span class="sxs-lookup"><span data-stu-id="73ab8-115">Create three qubit state $\frac{1}{\sqrt{2}}\ket{0}\_2(\ket{0}\_1\ket{0}_3+\ket{1}\_1\ket{1}_3)$:</span></span>

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a><span data-ttu-id="73ab8-116">参照</span><span class="sxs-lookup"><span data-stu-id="73ab8-116">See Also</span></span>

- [<span data-ttu-id="73ab8-117">Microsoft. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="73ab8-117">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="73ab8-118">Microsoft. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="73ab8-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="73ab8-119">Microsoft. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="73ab8-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)