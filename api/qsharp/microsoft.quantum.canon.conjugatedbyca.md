---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: acd5a9f796f751b9c9c374d841e80de9286fcd24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207311"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="3dee2-102">ConjugatedByCA 関数</span><span class="sxs-lookup"><span data-stu-id="3dee2-102">ConjugatedByCA function</span></span>

<span data-ttu-id="3dee2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3dee2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3dee2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dee2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dee2-105">外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dee2-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="3dee2-106">入力</span><span class="sxs-lookup"><span data-stu-id="3dee2-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="3dee2-107">outerOperation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="3dee2-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3dee2-108">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="3dee2-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="3dee2-109">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3dee2-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="3dee2-110">innerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3dee2-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3dee2-111">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="3dee2-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="3dee2-112">出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3dee2-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3dee2-113">そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="3dee2-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3dee2-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3dee2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3dee2-115">&</span><span class="sxs-lookup"><span data-stu-id="3dee2-115">'T</span></span>

<span data-ttu-id="3dee2-116">内部および外部の各操作が動作するターゲットの型。</span><span class="sxs-lookup"><span data-stu-id="3dee2-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="3dee2-117">解説</span><span class="sxs-lookup"><span data-stu-id="3dee2-117">Remarks</span></span>

<span data-ttu-id="3dee2-118">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3dee2-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="3dee2-119">参照</span><span class="sxs-lookup"><span data-stu-id="3dee2-119">See Also</span></span>

- [<span data-ttu-id="3dee2-120">Microsoft. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="3dee2-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="3dee2-121">Microsoft. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="3dee2-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="3dee2-122">Microsoft. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="3dee2-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="3dee2-123">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="3dee2-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)