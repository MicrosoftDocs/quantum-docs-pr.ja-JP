---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: 各インデックス操作の Applytoa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217614"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="a629d-102">各インデックス操作の Applytoa</span><span class="sxs-lookup"><span data-stu-id="a629d-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="a629d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a629d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a629d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a629d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a629d-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="a629d-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a629d-106">入力</span><span class="sxs-lookup"><span data-stu-id="a629d-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="a629d-107">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a629d-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a629d-108">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="a629d-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a629d-109">register: t []</span><span class="sxs-lookup"><span data-stu-id="a629d-109">register : 'T[]</span></span>

<span data-ttu-id="a629d-110">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="a629d-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a629d-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a629d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a629d-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a629d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a629d-113">&</span><span class="sxs-lookup"><span data-stu-id="a629d-113">'T</span></span>

<span data-ttu-id="a629d-114">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="a629d-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a629d-115">参照</span><span class="sxs-lookup"><span data-stu-id="a629d-115">See Also</span></span>

- [<span data-ttu-id="a629d-116">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="a629d-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="a629d-117">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="a629d-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="a629d-118">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="a629d-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="a629d-119">Microsoft........ の Indexca</span><span class="sxs-lookup"><span data-stu-id="a629d-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)