---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844623"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="78164-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="78164-102">ApplyToEach operation</span></span>

<span data-ttu-id="78164-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78164-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78164-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78164-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78164-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="78164-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="78164-106">入力</span><span class="sxs-lookup"><span data-stu-id="78164-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="78164-107">singleElementOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78164-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="78164-108">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="78164-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="78164-109">register: t []</span><span class="sxs-lookup"><span data-stu-id="78164-109">register : 'T[]</span></span>

<span data-ttu-id="78164-110">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="78164-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78164-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78164-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78164-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="78164-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78164-113">&</span><span class="sxs-lookup"><span data-stu-id="78164-113">'T</span></span>

<span data-ttu-id="78164-114">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="78164-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="78164-115">例</span><span class="sxs-lookup"><span data-stu-id="78164-115">Example</span></span>

<span data-ttu-id="78164-116">3 qubit $ \ket{+} $ 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="78164-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="78164-117">参照</span><span class="sxs-lookup"><span data-stu-id="78164-117">See Also</span></span>

- [<span data-ttu-id="78164-118">Microsoft................</span><span class="sxs-lookup"><span data-stu-id="78164-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="78164-119">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="78164-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="78164-120">Microsoft... の各 Ca</span><span class="sxs-lookup"><span data-stu-id="78164-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)