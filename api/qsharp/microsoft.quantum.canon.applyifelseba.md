---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844982"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="8f86f-102">ApplyIfElseBA 操作</span><span class="sxs-lookup"><span data-stu-id="8f86f-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="8f86f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f86f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f86f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f86f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f86f-105">従来のビットの値に応じて、2つの adjointable 操作のいずれかを適用します。</span><span class="sxs-lookup"><span data-stu-id="8f86f-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="8f86f-106">説明</span><span class="sxs-lookup"><span data-stu-id="8f86f-106">Description</span></span>

<span data-ttu-id="8f86f-107">が指定され `bit` `trueOp` ている `trueInput` 場合は、がのときの入力としての操作を適用 `bit` し、 `true` がのときに適用され `falseOp(falseInput)` `bit` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="8f86f-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="8f86f-108">入力</span><span class="sxs-lookup"><span data-stu-id="8f86f-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="8f86f-109">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f86f-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f86f-110">またはが適用されるかどうかを判断するために使用されるブール値 `trueOp` `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="8f86f-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj"></a><span data-ttu-id="8f86f-111">trueOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="8f86f-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8f86f-112">がの場合に適用される adjointable 操作 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="8f86f-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="8f86f-113">trueInput: t</span><span class="sxs-lookup"><span data-stu-id="8f86f-113">trueInput : 'T</span></span>

<span data-ttu-id="8f86f-114">がの場合に提供される入力 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="8f86f-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj"></a><span data-ttu-id="8f86f-115">False Op: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="8f86f-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8f86f-116">がの場合に適用される adjointable 操作 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="8f86f-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="8f86f-117">False 入力: ' U</span><span class="sxs-lookup"><span data-stu-id="8f86f-117">falseInput : 'U</span></span>

<span data-ttu-id="8f86f-118">がの場合に提供される入力 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="8f86f-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f86f-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f86f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f86f-120">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f86f-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f86f-121">&</span><span class="sxs-lookup"><span data-stu-id="8f86f-121">'T</span></span>

<span data-ttu-id="8f86f-122">`trueOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="8f86f-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="8f86f-123">' U</span><span class="sxs-lookup"><span data-stu-id="8f86f-123">'U</span></span>

<span data-ttu-id="8f86f-124">`falseOp`条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="8f86f-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f86f-125">参照</span><span class="sxs-lookup"><span data-stu-id="8f86f-125">See Also</span></span>

- [<span data-ttu-id="8f86f-126">Microsoft. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="8f86f-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="8f86f-127">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="8f86f-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="8f86f-128">Microsoft.....。</span><span class="sxs-lookup"><span data-stu-id="8f86f-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="8f86f-129">Microsoft... ".."</span><span class="sxs-lookup"><span data-stu-id="8f86f-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="8f86f-130">Microsoft. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="8f86f-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)