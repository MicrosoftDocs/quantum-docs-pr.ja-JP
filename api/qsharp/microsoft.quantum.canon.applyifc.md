---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718238"
---
# <a name="applyifc-operation"></a><span data-ttu-id="26c82-102">ApplyIfC 操作</span><span class="sxs-lookup"><span data-stu-id="26c82-102">ApplyIfC operation</span></span>

<span data-ttu-id="26c82-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26c82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26c82-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26c82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26c82-105">クラシックビットで条件付きの制御可能な操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="26c82-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="26c82-106">説明</span><span class="sxs-lookup"><span data-stu-id="26c82-106">Description</span></span>

<span data-ttu-id="26c82-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="26c82-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="26c82-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="26c82-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="26c82-109">サフィックスは、 `C` 適用される操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="26c82-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="26c82-110">入力</span><span class="sxs-lookup"><span data-stu-id="26c82-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="26c82-111">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="26c82-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="26c82-112">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="26c82-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="26c82-113">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26c82-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26c82-114">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="26c82-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="26c82-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="26c82-115">target : 'T</span></span>

<span data-ttu-id="26c82-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="26c82-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26c82-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26c82-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="26c82-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="26c82-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26c82-119">&</span><span class="sxs-lookup"><span data-stu-id="26c82-119">'T</span></span>

<span data-ttu-id="26c82-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="26c82-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="26c82-121">参照</span><span class="sxs-lookup"><span data-stu-id="26c82-121">See Also</span></span>

- [<span data-ttu-id="26c82-122">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="26c82-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="26c82-123">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="26c82-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="26c82-124">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="26c82-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)