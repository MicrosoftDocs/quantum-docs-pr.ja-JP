---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204931"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="b51c7-102">TransformedOperation 関数</span><span class="sxs-lookup"><span data-stu-id="b51c7-102">TransformedOperation function</span></span>

<span data-ttu-id="b51c7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b51c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b51c7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b51c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b51c7-105">関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b51c7-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="b51c7-106">入力</span><span class="sxs-lookup"><span data-stu-id="b51c7-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="b51c7-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="b51c7-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="b51c7-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="b51c7-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="b51c7-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b51c7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b51c7-110">変換する操作。</span><span class="sxs-lookup"><span data-stu-id="b51c7-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="b51c7-111">出力: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b51c7-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b51c7-112">新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。</span><span class="sxs-lookup"><span data-stu-id="b51c7-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b51c7-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b51c7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b51c7-114">&</span><span class="sxs-lookup"><span data-stu-id="b51c7-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b51c7-115">' U</span><span class="sxs-lookup"><span data-stu-id="b51c7-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="b51c7-116">参照</span><span class="sxs-lookup"><span data-stu-id="b51c7-116">See Also</span></span>

- [<span data-ttu-id="b51c7-117">Microsoft. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="b51c7-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="b51c7-118">Microsoft. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="b51c7-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="b51c7-119">Microsoft. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="b51c7-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="b51c7-120">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="b51c7-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="b51c7-121">Microsoft... Canon.</span><span class="sxs-lookup"><span data-stu-id="b51c7-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)