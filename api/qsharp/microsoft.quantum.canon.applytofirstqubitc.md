---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717409"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="04df5-102">ApplyToFirstQubitC 操作</span><span class="sxs-lookup"><span data-stu-id="04df5-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="04df5-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="04df5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="04df5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04df5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04df5-105">レジスタ内の最初の qubit に操作 op を適用します。</span><span class="sxs-lookup"><span data-stu-id="04df5-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="04df5-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="04df5-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="04df5-107">入力</span><span class="sxs-lookup"><span data-stu-id="04df5-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="04df5-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="04df5-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="04df5-109">最初の qubit に適用する操作</span><span class="sxs-lookup"><span data-stu-id="04df5-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="04df5-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04df5-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="04df5-111">操作が適用されている最初の qubit への qubit 配列</span><span class="sxs-lookup"><span data-stu-id="04df5-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="04df5-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04df5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="04df5-113">参照</span><span class="sxs-lookup"><span data-stu-id="04df5-113">See Also</span></span>

- [<span data-ttu-id="04df5-114">Microsoft... "."。</span><span class="sxs-lookup"><span data-stu-id="04df5-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)