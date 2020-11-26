---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Applywithinputトランス c 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 030c41d3ce0a5d613a95c6511f7278497ec5cda1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217171"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="f7076-102">Applywithinputトランス c 操作</span><span class="sxs-lookup"><span data-stu-id="f7076-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="f7076-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7076-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7076-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7076-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7076-105">入力を受け入れる操作、その操作と互換性のある出力を返す関数、およびその関数への入力を指定すると、関数を使用して操作が適用され、操作によって予期される形式に入力が変換されます。</span><span class="sxs-lookup"><span data-stu-id="f7076-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f7076-106">入力</span><span class="sxs-lookup"><span data-stu-id="f7076-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f7076-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="f7076-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f7076-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="f7076-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f7076-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="f7076-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f7076-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="f7076-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="f7076-111">入力: ' U</span><span class="sxs-lookup"><span data-stu-id="f7076-111">input : 'U</span></span>

<span data-ttu-id="f7076-112">関数への入力。</span><span class="sxs-lookup"><span data-stu-id="f7076-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7076-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7076-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7076-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7076-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7076-115">&</span><span class="sxs-lookup"><span data-stu-id="f7076-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="f7076-116">' U</span><span class="sxs-lookup"><span data-stu-id="f7076-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="f7076-117">参照</span><span class="sxs-lookup"><span data-stu-id="f7076-117">See Also</span></span>

- [<span data-ttu-id="f7076-118">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="f7076-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f7076-119">Microsoft.........。</span><span class="sxs-lookup"><span data-stu-id="f7076-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="f7076-120">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="f7076-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="f7076-121">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f7076-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)