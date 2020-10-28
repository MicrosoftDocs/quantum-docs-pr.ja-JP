---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: Applytofirstのすべての処理
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 502d876df0ed643c40ce6ee48eaf496a90b0f5dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717367"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="f02d7-102">Applytofirstのすべての処理</span><span class="sxs-lookup"><span data-stu-id="f02d7-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="f02d7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f02d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f02d7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f02d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f02d7-105">レジスタ内の最初の3つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="f02d7-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="f02d7-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f02d7-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f02d7-107">入力</span><span class="sxs-lookup"><span data-stu-id="f02d7-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj"></a><span data-ttu-id="f02d7-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)、[qubit](xref:microsoft.quantum.lang-ref.qubit)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="f02d7-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f02d7-109">最初の3つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="f02d7-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f02d7-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f02d7-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f02d7-111">操作が適用される最初の3つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="f02d7-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f02d7-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f02d7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f02d7-113">解説</span><span class="sxs-lookup"><span data-stu-id="f02d7-113">Remarks</span></span>

<span data-ttu-id="f02d7-114">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="f02d7-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="f02d7-115">参照</span><span class="sxs-lookup"><span data-stu-id="f02d7-115">See Also</span></span>

- [<span data-ttu-id="f02d7-116">Microsoft.........................</span><span class="sxs-lookup"><span data-stu-id="f02d7-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)