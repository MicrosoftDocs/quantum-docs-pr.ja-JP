---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715323"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="e00a1-102">TransformedOperationC 関数</span><span class="sxs-lookup"><span data-stu-id="e00a1-102">TransformedOperationC function</span></span>

<span data-ttu-id="e00a1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e00a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e00a1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e00a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e00a1-105">関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="e00a1-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e00a1-106">入力</span><span class="sxs-lookup"><span data-stu-id="e00a1-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e00a1-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="e00a1-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e00a1-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="e00a1-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="e00a1-109">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="e00a1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e00a1-110">変換する操作。</span><span class="sxs-lookup"><span data-stu-id="e00a1-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-ctl"></a><span data-ttu-id="e00a1-111">出力: ' U => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="e00a1-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e00a1-112">新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。</span><span class="sxs-lookup"><span data-stu-id="e00a1-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e00a1-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e00a1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e00a1-114">&</span><span class="sxs-lookup"><span data-stu-id="e00a1-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="e00a1-115">' U</span><span class="sxs-lookup"><span data-stu-id="e00a1-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e00a1-116">参照</span><span class="sxs-lookup"><span data-stu-id="e00a1-116">See Also</span></span>

- [<span data-ttu-id="e00a1-117">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="e00a1-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="e00a1-118">Microsoft. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="e00a1-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="e00a1-119">Microsoft. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="e00a1-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="e00a1-120">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="e00a1-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="e00a1-121">Microsoft... Canon.</span><span class="sxs-lookup"><span data-stu-id="e00a1-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)