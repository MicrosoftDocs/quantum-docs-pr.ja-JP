---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 622b1d93dcbd02d000a68de23c66537b24d36c99
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840837"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="02180-102">ConjugatedByC 関数</span><span class="sxs-lookup"><span data-stu-id="02180-102">ConjugatedByC function</span></span>

<span data-ttu-id="02180-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02180-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02180-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02180-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02180-105">外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。</span><span class="sxs-lookup"><span data-stu-id="02180-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="02180-106">入力</span><span class="sxs-lookup"><span data-stu-id="02180-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="02180-107">outerOperation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="02180-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="02180-108">$ $V を共役するために使用する必要がある操作 $U $。</span><span class="sxs-lookup"><span data-stu-id="02180-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="02180-109">外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="02180-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="02180-110">innerOperation: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="02180-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="02180-111">操作 $V $ conjugated。</span><span class="sxs-lookup"><span data-stu-id="02180-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="02180-112">出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="02180-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="02180-113">そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。</span><span class="sxs-lookup"><span data-stu-id="02180-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02180-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="02180-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02180-115">&</span><span class="sxs-lookup"><span data-stu-id="02180-115">'T</span></span>

<span data-ttu-id="02180-116">内部および外部の各操作が動作するターゲットの型。</span><span class="sxs-lookup"><span data-stu-id="02180-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="02180-117">解説</span><span class="sxs-lookup"><span data-stu-id="02180-117">Remarks</span></span>

<span data-ttu-id="02180-118">外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="02180-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="02180-119">参照</span><span class="sxs-lookup"><span data-stu-id="02180-119">See Also</span></span>

- [<span data-ttu-id="02180-120">Microsoft. ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="02180-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="02180-121">Microsoft. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="02180-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="02180-122">Microsoft. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="02180-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="02180-123">Microsoft.......</span><span class="sxs-lookup"><span data-stu-id="02180-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)