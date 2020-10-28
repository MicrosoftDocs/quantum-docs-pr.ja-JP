---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717591"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="a01e7-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="a01e7-102">ApplyToEach operation</span></span>

<span data-ttu-id="a01e7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a01e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a01e7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a01e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a01e7-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="a01e7-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a01e7-106">入力</span><span class="sxs-lookup"><span data-stu-id="a01e7-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="a01e7-107">singleElementOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a01e7-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a01e7-108">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="a01e7-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a01e7-109">register: t []</span><span class="sxs-lookup"><span data-stu-id="a01e7-109">register : 'T[]</span></span>

<span data-ttu-id="a01e7-110">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="a01e7-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a01e7-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a01e7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a01e7-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a01e7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a01e7-113">&</span><span class="sxs-lookup"><span data-stu-id="a01e7-113">'T</span></span>

<span data-ttu-id="a01e7-114">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="a01e7-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a01e7-115">参照</span><span class="sxs-lookup"><span data-stu-id="a01e7-115">See Also</span></span>

- [<span data-ttu-id="a01e7-116">Microsoft................</span><span class="sxs-lookup"><span data-stu-id="a01e7-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="a01e7-117">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="a01e7-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="a01e7-118">Microsoft... の各 Ca</span><span class="sxs-lookup"><span data-stu-id="a01e7-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)