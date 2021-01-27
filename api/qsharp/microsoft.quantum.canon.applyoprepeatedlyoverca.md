---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 9b7f0897009d9913fc886f99b2e29f3fc1040666
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841601"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="f8fb3-102">ApplyOpRepeatedlyOverCA 操作</span><span class="sxs-lookup"><span data-stu-id="f8fb3-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="f8fb3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f8fb3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f8fb3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8fb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8fb3-105">Qubit レジスタに対して同じ操作を複数回適用します。</span><span class="sxs-lookup"><span data-stu-id="f8fb3-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f8fb3-106">入力</span><span class="sxs-lookup"><span data-stu-id="f8fb3-106">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="f8fb3-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="f8fb3-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8fb3-108">Qubit レジスタに複数回適用される操作</span><span class="sxs-lookup"><span data-stu-id="f8fb3-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="f8fb3-109">ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="f8fb3-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="f8fb3-110">Op のターゲットを記述する入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="f8fb3-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="f8fb3-111">各配列には、使用する qubits を記述する整数のリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8fb3-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f8fb3-112">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8fb3-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8fb3-113">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="f8fb3-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8fb3-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8fb3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f8fb3-115">参照</span><span class="sxs-lookup"><span data-stu-id="f8fb3-115">See Also</span></span>

- [<span data-ttu-id="f8fb3-116">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="f8fb3-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)