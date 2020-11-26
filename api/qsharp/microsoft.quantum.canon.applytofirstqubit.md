---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 851f2b58a914c8b09188f442e442b91a8ede5416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217494"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="e1282-102">ApplyToFirstQubit 操作</span><span class="sxs-lookup"><span data-stu-id="e1282-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="e1282-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1282-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1282-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1282-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1282-105">レジスタ内の最初の qubit に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="e1282-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e1282-106">入力</span><span class="sxs-lookup"><span data-stu-id="e1282-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="e1282-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1282-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e1282-108">最初の qubit に適用する操作</span><span class="sxs-lookup"><span data-stu-id="e1282-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e1282-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1282-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e1282-110">操作が適用されている最初の qubit への qubit 配列</span><span class="sxs-lookup"><span data-stu-id="e1282-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1282-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1282-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e1282-112">参照</span><span class="sxs-lookup"><span data-stu-id="e1282-112">See Also</span></span>

- [<span data-ttu-id="e1282-113">Microsoft...、...。 ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="e1282-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="e1282-114">Microsoft.....。 ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="e1282-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="e1282-115">Microsoft. Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="e1282-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)