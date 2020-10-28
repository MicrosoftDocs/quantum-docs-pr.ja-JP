---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Applywithinputトランス c 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716844"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="bbb87-102">Applywithinputトランス c 操作</span><span class="sxs-lookup"><span data-stu-id="bbb87-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="bbb87-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bbb87-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bbb87-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbb87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbb87-105">入力を受け入れる操作、その操作と互換性のある出力を返す関数、およびその関数への入力を指定すると、関数を使用して操作が適用され、操作によって予期される形式に入力が変換されます。</span><span class="sxs-lookup"><span data-stu-id="bbb87-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="bbb87-106">入力</span><span class="sxs-lookup"><span data-stu-id="bbb87-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="bbb87-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="bbb87-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="bbb87-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="bbb87-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="bbb87-109">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="bbb87-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bbb87-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="bbb87-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="bbb87-111">入力: ' U</span><span class="sxs-lookup"><span data-stu-id="bbb87-111">input : 'U</span></span>

<span data-ttu-id="bbb87-112">関数への入力。</span><span class="sxs-lookup"><span data-stu-id="bbb87-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbb87-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbb87-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bbb87-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbb87-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbb87-115">&</span><span class="sxs-lookup"><span data-stu-id="bbb87-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="bbb87-116">' U</span><span class="sxs-lookup"><span data-stu-id="bbb87-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="bbb87-117">参照</span><span class="sxs-lookup"><span data-stu-id="bbb87-117">See Also</span></span>

- [<span data-ttu-id="bbb87-118">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="bbb87-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="bbb87-119">Microsoft.........。</span><span class="sxs-lookup"><span data-stu-id="bbb87-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="bbb87-120">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="bbb87-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="bbb87-121">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="bbb87-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)