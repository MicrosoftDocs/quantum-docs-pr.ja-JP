---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9f24c3ca9b152cf9bbf81e59b86f83a0ab459031
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841220"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="217b7-102">ApplyToSubregisterCA 操作</span><span class="sxs-lookup"><span data-stu-id="217b7-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="217b7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="217b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="217b7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="217b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="217b7-105">インデックスの配列によって指定された qubits を使用して、レジスタのサブレジスタに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="217b7-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="217b7-106">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="217b7-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="217b7-107">入力</span><span class="sxs-lookup"><span data-stu-id="217b7-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="217b7-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="217b7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="217b7-109">Subregister に適用する操作です。</span><span class="sxs-lookup"><span data-stu-id="217b7-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="217b7-110">idxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="217b7-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="217b7-111">操作が適用される qubits を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="217b7-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="217b7-112">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="217b7-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="217b7-113">操作が動作する登録です。</span><span class="sxs-lookup"><span data-stu-id="217b7-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="217b7-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="217b7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="217b7-115">参照</span><span class="sxs-lookup"><span data-stu-id="217b7-115">See Also</span></span>

- [<span data-ttu-id="217b7-116">Microsoft. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="217b7-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)