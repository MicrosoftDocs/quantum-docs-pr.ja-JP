---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: ApplyIfElseB 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 3eba3822a95939d210c5a05dd1efa80f1aa57374
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841834"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="fbe70-102">ApplyIfElseB 操作</span><span class="sxs-lookup"><span data-stu-id="fbe70-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="fbe70-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbe70-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbe70-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbe70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbe70-105">従来のビットの値に応じて、2つの操作のいずれかを適用します。</span><span class="sxs-lookup"><span data-stu-id="fbe70-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="fbe70-106">説明</span><span class="sxs-lookup"><span data-stu-id="fbe70-106">Description</span></span>

<span data-ttu-id="fbe70-107">が指定され `bit` `trueOp` ている `trueInput` 場合は、がのときの入力としての操作を適用 `bit` し、 `true` がのときに適用され `falseOp(falseInput)` `bit` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="fbe70-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="fbe70-108">入力</span><span class="sxs-lookup"><span data-stu-id="fbe70-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="fbe70-109">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fbe70-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fbe70-110">またはが適用されるかどうかを判断するために使用されるブール値 `trueOp` `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="fbe70-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="fbe70-111">trueOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbe70-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fbe70-112">がの場合に適用される操作 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="fbe70-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="fbe70-113">trueInput: t</span><span class="sxs-lookup"><span data-stu-id="fbe70-113">trueInput : 'T</span></span>

<span data-ttu-id="fbe70-114">がの場合に提供される入力 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="fbe70-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="fbe70-115">False Op: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbe70-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fbe70-116">がの場合に適用される操作 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="fbe70-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="fbe70-117">False 入力: ' U</span><span class="sxs-lookup"><span data-stu-id="fbe70-117">falseInput : 'U</span></span>

<span data-ttu-id="fbe70-118">がの場合に提供される入力 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="fbe70-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbe70-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbe70-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fbe70-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbe70-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbe70-121">&</span><span class="sxs-lookup"><span data-stu-id="fbe70-121">'T</span></span>

<span data-ttu-id="fbe70-122">`trueOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="fbe70-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="fbe70-123">' U</span><span class="sxs-lookup"><span data-stu-id="fbe70-123">'U</span></span>

<span data-ttu-id="fbe70-124">`falseOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="fbe70-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbe70-125">参照</span><span class="sxs-lookup"><span data-stu-id="fbe70-125">See Also</span></span>

- [<span data-ttu-id="fbe70-126">Microsoft. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="fbe70-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="fbe70-127">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="fbe70-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="fbe70-128">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="fbe70-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="fbe70-129">Microsoft... ".."</span><span class="sxs-lookup"><span data-stu-id="fbe70-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="fbe70-130">Microsoft. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="fbe70-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)