---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Applytofirst二つ Qubitsc 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717283"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="3ad84-102">Applytofirst二つ Qubitsc 操作</span><span class="sxs-lookup"><span data-stu-id="3ad84-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="3ad84-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3ad84-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3ad84-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ad84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ad84-105">レジスタ内の最初の2つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="3ad84-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="3ad84-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ad84-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3ad84-107">入力</span><span class="sxs-lookup"><span data-stu-id="3ad84-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="3ad84-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="3ad84-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3ad84-109">最初の2つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="3ad84-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3ad84-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3ad84-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3ad84-111">操作が適用される最初の2つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="3ad84-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ad84-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ad84-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ad84-113">解説</span><span class="sxs-lookup"><span data-stu-id="3ad84-113">Remarks</span></span>

<span data-ttu-id="3ad84-114">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="3ad84-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="3ad84-115">参照</span><span class="sxs-lookup"><span data-stu-id="3ad84-115">See Also</span></span>

- [<span data-ttu-id="3ad84-116">Microsoft. Canon. Applytofirstの場合</span><span class="sxs-lookup"><span data-stu-id="3ad84-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)