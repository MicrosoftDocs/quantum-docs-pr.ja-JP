---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717404"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="bac2a-102">ApplyToFirstQubitA 操作</span><span class="sxs-lookup"><span data-stu-id="bac2a-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="bac2a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bac2a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bac2a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bac2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bac2a-105">レジスタ内の最初の qubit に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="bac2a-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="bac2a-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="bac2a-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bac2a-107">入力</span><span class="sxs-lookup"><span data-stu-id="bac2a-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="bac2a-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="bac2a-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bac2a-109">最初の qubit に適用する操作</span><span class="sxs-lookup"><span data-stu-id="bac2a-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="bac2a-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bac2a-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bac2a-111">操作が適用されている最初の qubit への qubit 配列</span><span class="sxs-lookup"><span data-stu-id="bac2a-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="bac2a-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bac2a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bac2a-113">参照</span><span class="sxs-lookup"><span data-stu-id="bac2a-113">See Also</span></span>

- [<span data-ttu-id="bac2a-114">Microsoft... "."。</span><span class="sxs-lookup"><span data-stu-id="bac2a-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)