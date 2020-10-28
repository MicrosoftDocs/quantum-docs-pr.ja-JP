---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 970acfbc63bc95542827988c5c81387e8812f289
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717824"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="3935f-102">ApplyOpRepeatedlyOverCA 操作</span><span class="sxs-lookup"><span data-stu-id="3935f-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="3935f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3935f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3935f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3935f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3935f-105">Qubit レジスタに対して同じ操作を複数回適用します。</span><span class="sxs-lookup"><span data-stu-id="3935f-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3935f-106">入力</span><span class="sxs-lookup"><span data-stu-id="3935f-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="3935f-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="3935f-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3935f-108">Qubit レジスタに複数回適用される操作</span><span class="sxs-lookup"><span data-stu-id="3935f-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="3935f-109">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="3935f-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="3935f-110">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="3935f-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="3935f-111">各配列には、使用する qubits を記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3935f-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3935f-112">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3935f-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3935f-113">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="3935f-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3935f-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3935f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3935f-115">参照</span><span class="sxs-lookup"><span data-stu-id="3935f-115">See Also</span></span>

- [<span data-ttu-id="3935f-116">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="3935f-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)