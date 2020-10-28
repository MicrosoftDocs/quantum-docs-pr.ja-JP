---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Applytofirst二つ Qubitsa 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717306"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="4c7a7-102">Applytofirst二つ Qubitsa 操作</span><span class="sxs-lookup"><span data-stu-id="4c7a7-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="4c7a7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c7a7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c7a7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c7a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c7a7-105">レジスタ内の最初の2つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="4c7a7-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="4c7a7-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="4c7a7-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4c7a7-107">入力</span><span class="sxs-lookup"><span data-stu-id="4c7a7-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="4c7a7-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="4c7a7-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4c7a7-109">最初の2つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="4c7a7-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="4c7a7-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4c7a7-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4c7a7-111">操作が適用される最初の2つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="4c7a7-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c7a7-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c7a7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4c7a7-113">解説</span><span class="sxs-lookup"><span data-stu-id="4c7a7-113">Remarks</span></span>

<span data-ttu-id="4c7a7-114">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="4c7a7-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="4c7a7-115">参照</span><span class="sxs-lookup"><span data-stu-id="4c7a7-115">See Also</span></span>

- [<span data-ttu-id="4c7a7-116">Microsoft. Canon. Applytofirstの場合</span><span class="sxs-lookup"><span data-stu-id="4c7a7-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)