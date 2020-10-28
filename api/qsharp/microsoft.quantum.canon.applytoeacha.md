---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: 各操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717577"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="76f7e-102">各操作の適用</span><span class="sxs-lookup"><span data-stu-id="76f7e-102">ApplyToEachA operation</span></span>

<span data-ttu-id="76f7e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76f7e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76f7e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76f7e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76f7e-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="76f7e-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="76f7e-106">修飾子は、 `A` single qubit 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="76f7e-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="76f7e-107">入力</span><span class="sxs-lookup"><span data-stu-id="76f7e-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="76f7e-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="76f7e-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="76f7e-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="76f7e-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="76f7e-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="76f7e-110">register : 'T[]</span></span>

<span data-ttu-id="76f7e-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="76f7e-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76f7e-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76f7e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76f7e-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="76f7e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76f7e-114">&</span><span class="sxs-lookup"><span data-stu-id="76f7e-114">'T</span></span>

<span data-ttu-id="76f7e-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="76f7e-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="76f7e-116">参照</span><span class="sxs-lookup"><span data-stu-id="76f7e-116">See Also</span></span>

- [<span data-ttu-id="76f7e-117">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="76f7e-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)