---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: Applytofirstのすべての実行操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9bc5248b5de0db60f54bbec4cb33dde1160c2b41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841389"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="dedcf-102">Applytofirstのすべての実行操作</span><span class="sxs-lookup"><span data-stu-id="dedcf-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="dedcf-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dedcf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dedcf-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dedcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dedcf-105">レジスタ内の最初の3つの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="dedcf-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="dedcf-106">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="dedcf-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dedcf-107">入力</span><span class="sxs-lookup"><span data-stu-id="dedcf-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="dedcf-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)、[qubit](xref:microsoft.quantum.lang-ref.qubit)、[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="dedcf-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dedcf-109">最初の3つの qubits に適用する操作</span><span class="sxs-lookup"><span data-stu-id="dedcf-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="dedcf-110">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dedcf-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dedcf-111">操作が適用される最初の3つの qubit への qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="dedcf-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dedcf-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dedcf-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dedcf-113">解説</span><span class="sxs-lookup"><span data-stu-id="dedcf-113">Remarks</span></span>

<span data-ttu-id="dedcf-114">このようにすると、次の記述と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="dedcf-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="dedcf-115">参照</span><span class="sxs-lookup"><span data-stu-id="dedcf-115">See Also</span></span>

- [<span data-ttu-id="dedcf-116">Microsoft.........................</span><span class="sxs-lookup"><span data-stu-id="dedcf-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)