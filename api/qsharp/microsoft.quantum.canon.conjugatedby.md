---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716471"
---
# <a name="conjugatedby-function"></a><span data-ttu-id="948ea-102">ConjugatedBy 関数</span><span class="sxs-lookup"><span data-stu-id="948ea-102">ConjugatedBy function</span></span>

<span data-ttu-id="948ea-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="948ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="948ea-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="948ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="948ea-105">外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="948ea-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="948ea-106">入力</span><span class="sxs-lookup"><span data-stu-id="948ea-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="948ea-107">outerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="948ea-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="948ea-108">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="948ea-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="948ea-109">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="948ea-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="948ea-110">innerOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="948ea-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="948ea-111">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="948ea-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="948ea-112">出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="948ea-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="948ea-113">そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="948ea-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="948ea-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="948ea-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="948ea-115">&</span><span class="sxs-lookup"><span data-stu-id="948ea-115">'T</span></span>

<span data-ttu-id="948ea-116">内部および外部の各操作が動作するターゲットの型。</span><span class="sxs-lookup"><span data-stu-id="948ea-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="948ea-117">解説</span><span class="sxs-lookup"><span data-stu-id="948ea-117">Remarks</span></span>

<span data-ttu-id="948ea-118">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="948ea-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="948ea-119">参照</span><span class="sxs-lookup"><span data-stu-id="948ea-119">See Also</span></span>

- [<span data-ttu-id="948ea-120">Microsoft. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="948ea-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="948ea-121">Microsoft. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="948ea-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="948ea-122">Microsoft. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="948ea-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="948ea-123">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="948ea-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)