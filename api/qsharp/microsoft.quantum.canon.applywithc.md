---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716900"
---
# <a name="applywithc-operation"></a><span data-ttu-id="a8ba9-102">ApplyWithC 操作</span><span class="sxs-lookup"><span data-stu-id="a8ba9-102">ApplyWithC operation</span></span>

<span data-ttu-id="a8ba9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8ba9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8ba9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8ba9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8ba9-105">2つの操作を指定した場合、1つは conjugated として適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="a8ba9-106">説明</span><span class="sxs-lookup"><span data-stu-id="a8ba9-106">Description</span></span>

<span data-ttu-id="a8ba9-107">指定された2つの操作は、それぞれが $U $ および $V $ という順序で記述されていますが、これらはシーケンス $U ^ {\ dagger} V U $ に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="a8ba9-108">つまり、この操作では、$V $ conjugated によって指定された、$U $ のユニタリ演算子が実装されます。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="a8ba9-109">入力</span><span class="sxs-lookup"><span data-stu-id="a8ba9-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="a8ba9-110">outerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="a8ba9-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a8ba9-111">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="a8ba9-112">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="a8ba9-113">innerOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="a8ba9-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a8ba9-114">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="a8ba9-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="a8ba9-115">target : 'T</span></span>

<span data-ttu-id="a8ba9-116">外部操作と内部操作に提供する入力。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8ba9-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8ba9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8ba9-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8ba9-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8ba9-119">&</span><span class="sxs-lookup"><span data-stu-id="a8ba9-119">'T</span></span>

<span data-ttu-id="a8ba9-120">内部および外部の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8ba9-121">解説</span><span class="sxs-lookup"><span data-stu-id="a8ba9-121">Remarks</span></span>

<span data-ttu-id="a8ba9-122">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8ba9-123">参照</span><span class="sxs-lookup"><span data-stu-id="a8ba9-123">See Also</span></span>

- [<span data-ttu-id="a8ba9-124">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="a8ba9-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="a8ba9-125">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="a8ba9-126">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="a8ba9-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)