---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Applywithinputトランス操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716849"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="2f5fc-102">Applywithinputトランス操作</span><span class="sxs-lookup"><span data-stu-id="2f5fc-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="2f5fc-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f5fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f5fc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f5fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f5fc-105">入力を受け入れる操作、その操作と互換性のある出力を返す関数、およびその関数への入力を指定すると、関数を使用して操作が適用され、操作によって予期される形式に入力が変換されます。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2f5fc-106">入力</span><span class="sxs-lookup"><span data-stu-id="2f5fc-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="2f5fc-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="2f5fc-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="2f5fc-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="2f5fc-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="2f5fc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2f5fc-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="2f5fc-111">入力: ' U</span><span class="sxs-lookup"><span data-stu-id="2f5fc-111">input : 'U</span></span>

<span data-ttu-id="2f5fc-112">関数への入力。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f5fc-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f5fc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f5fc-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f5fc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f5fc-115">&</span><span class="sxs-lookup"><span data-stu-id="2f5fc-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="2f5fc-116">' U</span><span class="sxs-lookup"><span data-stu-id="2f5fc-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="2f5fc-117">参照</span><span class="sxs-lookup"><span data-stu-id="2f5fc-117">See Also</span></span>

- [<span data-ttu-id="2f5fc-118">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="2f5fc-119">Microsoft............。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="2f5fc-120">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="2f5fc-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="2f5fc-121">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="2f5fc-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)