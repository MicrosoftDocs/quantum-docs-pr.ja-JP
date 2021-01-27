---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 393db9f8ce092100abc157ace1ee9fbbb3b06d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850383"
---
# <a name="applywithc-operation"></a><span data-ttu-id="fe696-102">ApplyWithC 操作</span><span class="sxs-lookup"><span data-stu-id="fe696-102">ApplyWithC operation</span></span>

<span data-ttu-id="fe696-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fe696-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fe696-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe696-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe696-105">2つの操作を指定した場合、1つは conjugated として適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe696-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="fe696-106">説明</span><span class="sxs-lookup"><span data-stu-id="fe696-106">Description</span></span>

<span data-ttu-id="fe696-107">指定された2つの操作は、それぞれが $U $ および $V $ という順序で記述されていますが、これらはシーケンス $U ^ {\ dagger} V U $ に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe696-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="fe696-108">つまり、この操作では、$V $ conjugated によって指定された、$U $ のユニタリ演算子が実装されます。</span><span class="sxs-lookup"><span data-stu-id="fe696-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="fe696-109">入力</span><span class="sxs-lookup"><span data-stu-id="fe696-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="fe696-110">outerOperation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="fe696-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fe696-111">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="fe696-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="fe696-112">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fe696-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="fe696-113">innerOperation: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="fe696-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fe696-114">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="fe696-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="fe696-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="fe696-115">target : 'T</span></span>

<span data-ttu-id="fe696-116">外部操作と内部操作に提供する入力。</span><span class="sxs-lookup"><span data-stu-id="fe696-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe696-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe696-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fe696-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe696-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe696-119">&</span><span class="sxs-lookup"><span data-stu-id="fe696-119">'T</span></span>

<span data-ttu-id="fe696-120">内部および外部の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="fe696-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe696-121">解説</span><span class="sxs-lookup"><span data-stu-id="fe696-121">Remarks</span></span>

<span data-ttu-id="fe696-122">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fe696-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe696-123">参照</span><span class="sxs-lookup"><span data-stu-id="fe696-123">See Also</span></span>

- [<span data-ttu-id="fe696-124">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="fe696-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="fe696-125">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="fe696-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="fe696-126">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="fe696-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)