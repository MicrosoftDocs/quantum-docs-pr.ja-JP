---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717395"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="615d9-102">ApplyToFirstQubitCA 操作</span><span class="sxs-lookup"><span data-stu-id="615d9-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="615d9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="615d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="615d9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="615d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="615d9-105">レジスタ内の最初の qubit に操作 op を適用します。</span><span class="sxs-lookup"><span data-stu-id="615d9-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="615d9-106">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="615d9-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="615d9-107">入力</span><span class="sxs-lookup"><span data-stu-id="615d9-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="615d9-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="615d9-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="615d9-109">最初の qubit に適用する操作</span><span class="sxs-lookup"><span data-stu-id="615d9-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="615d9-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="615d9-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="615d9-111">操作が適用されている最初の qubit への qubit 配列</span><span class="sxs-lookup"><span data-stu-id="615d9-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="615d9-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="615d9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="615d9-113">参照</span><span class="sxs-lookup"><span data-stu-id="615d9-113">See Also</span></span>

- [<span data-ttu-id="615d9-114">Microsoft... "."。</span><span class="sxs-lookup"><span data-stu-id="615d9-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)