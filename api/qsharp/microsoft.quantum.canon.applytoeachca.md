---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: 各 Ca 操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717549"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="01ccb-102">各 Ca 操作の適用</span><span class="sxs-lookup"><span data-stu-id="01ccb-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="01ccb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01ccb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01ccb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01ccb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01ccb-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="01ccb-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="01ccb-106">修飾子は、 `CA` single qubit 操作が制御可能で adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="01ccb-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="01ccb-107">入力</span><span class="sxs-lookup"><span data-stu-id="01ccb-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="01ccb-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="01ccb-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="01ccb-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="01ccb-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="01ccb-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="01ccb-110">register : 'T[]</span></span>

<span data-ttu-id="01ccb-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="01ccb-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01ccb-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01ccb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="01ccb-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="01ccb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01ccb-114">&</span><span class="sxs-lookup"><span data-stu-id="01ccb-114">'T</span></span>

<span data-ttu-id="01ccb-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="01ccb-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="01ccb-116">参照</span><span class="sxs-lookup"><span data-stu-id="01ccb-116">See Also</span></span>

- [<span data-ttu-id="01ccb-117">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="01ccb-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)