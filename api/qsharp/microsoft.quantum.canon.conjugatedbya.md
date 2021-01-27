---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 141c42d335add85103e16598264f781f32ab80fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840851"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="5ae12-102">ConjugatedByA 関数</span><span class="sxs-lookup"><span data-stu-id="5ae12-102">ConjugatedByA function</span></span>

<span data-ttu-id="5ae12-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ae12-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ae12-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ae12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ae12-105">外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="5ae12-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="5ae12-106">入力</span><span class="sxs-lookup"><span data-stu-id="5ae12-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="5ae12-107">outerOperation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="5ae12-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ae12-108">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="5ae12-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="5ae12-109">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5ae12-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="5ae12-110">innerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="5ae12-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ae12-111">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="5ae12-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="5ae12-112">出力: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="5ae12-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ae12-113">そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="5ae12-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5ae12-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ae12-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ae12-115">&</span><span class="sxs-lookup"><span data-stu-id="5ae12-115">'T</span></span>

<span data-ttu-id="5ae12-116">内部および外部の各操作が動作するターゲットの型。</span><span class="sxs-lookup"><span data-stu-id="5ae12-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ae12-117">解説</span><span class="sxs-lookup"><span data-stu-id="5ae12-117">Remarks</span></span>

<span data-ttu-id="5ae12-118">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5ae12-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ae12-119">参照</span><span class="sxs-lookup"><span data-stu-id="5ae12-119">See Also</span></span>

- [<span data-ttu-id="5ae12-120">Microsoft. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="5ae12-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="5ae12-121">Microsoft. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="5ae12-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="5ae12-122">Microsoft. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="5ae12-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="5ae12-123">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="5ae12-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)