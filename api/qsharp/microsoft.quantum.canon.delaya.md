---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207141"
---
# <a name="delaya-operation"></a><span data-ttu-id="f9f4c-102">DelayA 操作</span><span class="sxs-lookup"><span data-stu-id="f9f4c-102">DelayA operation</span></span>

<span data-ttu-id="f9f4c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9f4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9f4c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9f4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9f4c-105">指定された操作を遅延付きで適用します。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="f9f4c-106">説明</span><span class="sxs-lookup"><span data-stu-id="f9f4c-106">Description</span></span>

<span data-ttu-id="f9f4c-107">操作とその操作への入力を指定した場合、追加の入力が提供されると、によって操作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="f9f4c-108">特に、式 `Delay(op, arg, _)` は、 `op` 呼び出されたときにに適用される演算です `arg` 。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="f9f4c-109">式 `Delay(op,arg,_)` を使用すると、のアプリケーションを遅延させることができ `op` ます。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="f9f4c-110">入力</span><span class="sxs-lookup"><span data-stu-id="f9f4c-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f9f4c-111">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="f9f4c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f9f4c-112">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="f9f4c-113">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="f9f4c-113">arg : 'T</span></span>

<span data-ttu-id="f9f4c-114">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="f9f4c-115">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9f4c-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="f9f4c-116">部分アプリケーションを使用して操作のアプリケーションを遅延させるために使用される引数。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9f4c-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9f4c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9f4c-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9f4c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9f4c-119">&</span><span class="sxs-lookup"><span data-stu-id="f9f4c-119">'T</span></span>

<span data-ttu-id="f9f4c-120">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="f9f4c-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9f4c-121">参照</span><span class="sxs-lookup"><span data-stu-id="f9f4c-121">See Also</span></span>

- [<span data-ttu-id="f9f4c-122">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="f9f4c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="f9f4c-123">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="f9f4c-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)