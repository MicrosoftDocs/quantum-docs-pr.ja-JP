---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716270"
---
# <a name="delayca-operation"></a><span data-ttu-id="7a8f2-102">DelayCA 操作</span><span class="sxs-lookup"><span data-stu-id="7a8f2-102">DelayCA operation</span></span>

<span data-ttu-id="7a8f2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a8f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a8f2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a8f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a8f2-105">指定された操作を遅延付きで適用します。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="7a8f2-106">説明</span><span class="sxs-lookup"><span data-stu-id="7a8f2-106">Description</span></span>

<span data-ttu-id="7a8f2-107">操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="7a8f2-108">特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="7a8f2-109">式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="7a8f2-110">入力</span><span class="sxs-lookup"><span data-stu-id="7a8f2-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="7a8f2-111">op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="7a8f2-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="7a8f2-112">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="7a8f2-113">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="7a8f2-113">arg : 'T</span></span>

<span data-ttu-id="7a8f2-114">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="7a8f2-115">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a8f2-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="7a8f2-116">部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a8f2-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a8f2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7a8f2-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a8f2-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a8f2-119">&</span><span class="sxs-lookup"><span data-stu-id="7a8f2-119">'T</span></span>

<span data-ttu-id="7a8f2-120">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="7a8f2-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a8f2-121">参照</span><span class="sxs-lookup"><span data-stu-id="7a8f2-121">See Also</span></span>

- [<span data-ttu-id="7a8f2-122">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="7a8f2-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="7a8f2-123">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="7a8f2-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)