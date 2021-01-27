---
uid: Microsoft.Quantum.Canon.Delay
title: 遅延操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840657"
---
# <a name="delay-operation"></a><span data-ttu-id="2f333-102">遅延操作</span><span class="sxs-lookup"><span data-stu-id="2f333-102">Delay operation</span></span>

<span data-ttu-id="2f333-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f333-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f333-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f333-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f333-105">指定された操作を遅延付きで適用します。</span><span class="sxs-lookup"><span data-stu-id="2f333-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="2f333-106">説明</span><span class="sxs-lookup"><span data-stu-id="2f333-106">Description</span></span>

<span data-ttu-id="2f333-107">操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2f333-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="2f333-108">特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。</span><span class="sxs-lookup"><span data-stu-id="2f333-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="2f333-109">式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。</span><span class="sxs-lookup"><span data-stu-id="2f333-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="2f333-110">入力</span><span class="sxs-lookup"><span data-stu-id="2f333-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="2f333-111">op: t => ' U</span><span class="sxs-lookup"><span data-stu-id="2f333-111">op : 'T => 'U</span></span> 

<span data-ttu-id="2f333-112">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="2f333-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="2f333-113">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="2f333-113">arg : 'T</span></span>

<span data-ttu-id="2f333-114">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="2f333-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="2f333-115">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f333-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="2f333-116">部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。</span><span class="sxs-lookup"><span data-stu-id="2f333-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="2f333-117">出力: ' U</span><span class="sxs-lookup"><span data-stu-id="2f333-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f333-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f333-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f333-119">&</span><span class="sxs-lookup"><span data-stu-id="2f333-119">'T</span></span>

<span data-ttu-id="2f333-120">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="2f333-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="2f333-121">' U</span><span class="sxs-lookup"><span data-stu-id="2f333-121">'U</span></span>

<span data-ttu-id="2f333-122">遅延する操作の戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="2f333-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f333-123">参照</span><span class="sxs-lookup"><span data-stu-id="2f333-123">See Also</span></span>

- [<span data-ttu-id="2f333-124">Microsoft.. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="2f333-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="2f333-125">Microsoft の Quantum... DelayA</span><span class="sxs-lookup"><span data-stu-id="2f333-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="2f333-126">Microsoft. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="2f333-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="2f333-127">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="2f333-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)