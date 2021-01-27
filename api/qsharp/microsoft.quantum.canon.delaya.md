---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c7385cfcdf782347feb8d95311205a9311f4c929
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840660"
---
# <a name="delaya-operation"></a><span data-ttu-id="e8634-102">DelayA 操作</span><span class="sxs-lookup"><span data-stu-id="e8634-102">DelayA operation</span></span>

<span data-ttu-id="e8634-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e8634-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e8634-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8634-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8634-105">指定された操作を遅延付きで適用します。</span><span class="sxs-lookup"><span data-stu-id="e8634-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e8634-106">説明</span><span class="sxs-lookup"><span data-stu-id="e8634-106">Description</span></span>

<span data-ttu-id="e8634-107">操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e8634-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="e8634-108">特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。</span><span class="sxs-lookup"><span data-stu-id="e8634-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="e8634-109">式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。</span><span class="sxs-lookup"><span data-stu-id="e8634-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="e8634-110">入力</span><span class="sxs-lookup"><span data-stu-id="e8634-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e8634-111">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="e8634-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e8634-112">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="e8634-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="e8634-113">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="e8634-113">arg : 'T</span></span>

<span data-ttu-id="e8634-114">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="e8634-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="e8634-115">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8634-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="e8634-116">部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。</span><span class="sxs-lookup"><span data-stu-id="e8634-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8634-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8634-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8634-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8634-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8634-119">&</span><span class="sxs-lookup"><span data-stu-id="e8634-119">'T</span></span>

<span data-ttu-id="e8634-120">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="e8634-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8634-121">参照</span><span class="sxs-lookup"><span data-stu-id="e8634-121">See Also</span></span>

- [<span data-ttu-id="e8634-122">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e8634-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="e8634-123">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="e8634-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)