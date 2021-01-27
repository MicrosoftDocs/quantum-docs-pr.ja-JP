---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Applytofirst、"操作"
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850697"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="1f7e4-102">Applytofirst、"操作"</span><span class="sxs-lookup"><span data-stu-id="1f7e4-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="1f7e4-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f7e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f7e4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f7e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f7e4-105">レジスタ内の最初の3つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="1f7e4-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1f7e4-106">入力</span><span class="sxs-lookup"><span data-stu-id="1f7e4-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="1f7e4-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)、[qubit](xref:microsoft.quantum.lang-ref.qubit)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f7e4-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1f7e4-108">最初の3つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="1f7e4-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1f7e4-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f7e4-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f7e4-110">操作が適用される最初の3つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="1f7e4-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f7e4-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f7e4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1f7e4-112">解説</span><span class="sxs-lookup"><span data-stu-id="1f7e4-112">Remarks</span></span>

<span data-ttu-id="1f7e4-113">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="1f7e4-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="1f7e4-114">参照</span><span class="sxs-lookup"><span data-stu-id="1f7e4-114">See Also</span></span>

- [<span data-ttu-id="1f7e4-115">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="1f7e4-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="1f7e4-116">Microsoft.........................</span><span class="sxs-lookup"><span data-stu-id="1f7e4-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="1f7e4-117">Microsoft.........................</span><span class="sxs-lookup"><span data-stu-id="1f7e4-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)