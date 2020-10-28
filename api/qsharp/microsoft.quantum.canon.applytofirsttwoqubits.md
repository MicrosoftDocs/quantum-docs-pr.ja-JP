---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717311"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="7bbc7-102">ApplyToFirstTwoQubits 操作</span><span class="sxs-lookup"><span data-stu-id="7bbc7-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="7bbc7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7bbc7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7bbc7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bbc7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bbc7-105">レジスタ内の最初の2つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7bbc7-106">入力</span><span class="sxs-lookup"><span data-stu-id="7bbc7-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="7bbc7-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bbc7-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7bbc7-108">最初の2つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="7bbc7-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="7bbc7-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7bbc7-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7bbc7-110">操作が適用される最初の2つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7bbc7-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bbc7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7bbc7-112">解説</span><span class="sxs-lookup"><span data-stu-id="7bbc7-112">Remarks</span></span>

<span data-ttu-id="7bbc7-113">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="7bbc7-114">参照</span><span class="sxs-lookup"><span data-stu-id="7bbc7-114">See Also</span></span>

- [<span data-ttu-id="7bbc7-115">Microsoft. Canon. Applytofirstの場合</span><span class="sxs-lookup"><span data-stu-id="7bbc7-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="7bbc7-116">Microsoft. Canon. Applytofirstbitsc</span><span class="sxs-lookup"><span data-stu-id="7bbc7-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="7bbc7-117">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)