---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216491"
---
# <a name="delayc-operation"></a><span data-ttu-id="a54eb-102">DelayC 操作</span><span class="sxs-lookup"><span data-stu-id="a54eb-102">DelayC operation</span></span>

<span data-ttu-id="a54eb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a54eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a54eb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a54eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a54eb-105">指定された操作を遅延付きで適用します。</span><span class="sxs-lookup"><span data-stu-id="a54eb-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="a54eb-106">説明</span><span class="sxs-lookup"><span data-stu-id="a54eb-106">Description</span></span>

<span data-ttu-id="a54eb-107">操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a54eb-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="a54eb-108">特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。</span><span class="sxs-lookup"><span data-stu-id="a54eb-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="a54eb-109">式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。</span><span class="sxs-lookup"><span data-stu-id="a54eb-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="a54eb-110">入力</span><span class="sxs-lookup"><span data-stu-id="a54eb-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="a54eb-111">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="a54eb-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a54eb-112">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="a54eb-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="a54eb-113">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="a54eb-113">arg : 'T</span></span>

<span data-ttu-id="a54eb-114">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="a54eb-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="a54eb-115">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a54eb-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a54eb-116">部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。</span><span class="sxs-lookup"><span data-stu-id="a54eb-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a54eb-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a54eb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a54eb-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a54eb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a54eb-119">&</span><span class="sxs-lookup"><span data-stu-id="a54eb-119">'T</span></span>

<span data-ttu-id="a54eb-120">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="a54eb-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a54eb-121">参照</span><span class="sxs-lookup"><span data-stu-id="a54eb-121">See Also</span></span>

- [<span data-ttu-id="a54eb-122">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a54eb-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="a54eb-123">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="a54eb-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)