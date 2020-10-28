---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 349424a102dba7354bbaa65fffdc2b5d506a3b91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715332"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="8dc52-102">TransformedOperationA 関数</span><span class="sxs-lookup"><span data-stu-id="8dc52-102">TransformedOperationA function</span></span>

<span data-ttu-id="8dc52-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8dc52-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8dc52-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8dc52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8dc52-105">関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="8dc52-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8dc52-106">入力</span><span class="sxs-lookup"><span data-stu-id="8dc52-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8dc52-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="8dc52-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8dc52-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="8dc52-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="8dc52-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="8dc52-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8dc52-110">変換する操作。</span><span class="sxs-lookup"><span data-stu-id="8dc52-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj"></a><span data-ttu-id="8dc52-111">出力: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="8dc52-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8dc52-112">新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。</span><span class="sxs-lookup"><span data-stu-id="8dc52-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8dc52-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dc52-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8dc52-114">&</span><span class="sxs-lookup"><span data-stu-id="8dc52-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="8dc52-115">' U</span><span class="sxs-lookup"><span data-stu-id="8dc52-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="8dc52-116">参照</span><span class="sxs-lookup"><span data-stu-id="8dc52-116">See Also</span></span>

- [<span data-ttu-id="8dc52-117">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="8dc52-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="8dc52-118">Microsoft. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="8dc52-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="8dc52-119">Microsoft. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="8dc52-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="8dc52-120">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="8dc52-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="8dc52-121">Microsoft... Canon.</span><span class="sxs-lookup"><span data-stu-id="8dc52-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)