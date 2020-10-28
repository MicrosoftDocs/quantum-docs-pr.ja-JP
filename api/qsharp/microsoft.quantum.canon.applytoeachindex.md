---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: 各インデックス操作の Applytoa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717544"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="120dc-102">各インデックス操作の Applytoa</span><span class="sxs-lookup"><span data-stu-id="120dc-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="120dc-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="120dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="120dc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="120dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="120dc-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="120dc-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="120dc-106">入力</span><span class="sxs-lookup"><span data-stu-id="120dc-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="120dc-107">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="120dc-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="120dc-108">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="120dc-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="120dc-109">register: t []</span><span class="sxs-lookup"><span data-stu-id="120dc-109">register : 'T[]</span></span>

<span data-ttu-id="120dc-110">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="120dc-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="120dc-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="120dc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="120dc-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="120dc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="120dc-113">&</span><span class="sxs-lookup"><span data-stu-id="120dc-113">'T</span></span>

<span data-ttu-id="120dc-114">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="120dc-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="120dc-115">参照</span><span class="sxs-lookup"><span data-stu-id="120dc-115">See Also</span></span>

- [<span data-ttu-id="120dc-116">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="120dc-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="120dc-117">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="120dc-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="120dc-118">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="120dc-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="120dc-119">Microsoft........ の Indexca</span><span class="sxs-lookup"><span data-stu-id="120dc-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)