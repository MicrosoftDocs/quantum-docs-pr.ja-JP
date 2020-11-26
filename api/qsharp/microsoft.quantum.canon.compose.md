---
uid: Microsoft.Quantum.Canon.Compose
title: 関数の作成
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216763"
---
# <a name="compose-function"></a><span data-ttu-id="ac3bf-102">関数の作成</span><span class="sxs-lookup"><span data-stu-id="ac3bf-102">Compose function</span></span>

<span data-ttu-id="ac3bf-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac3bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac3bf-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac3bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac3bf-105">2つの関数の合成を返します。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="ac3bf-106">説明</span><span class="sxs-lookup"><span data-stu-id="ac3bf-106">Description</span></span>

<span data-ttu-id="ac3bf-107">$ および $g $ $f 2 つの関数が指定されている場合、$f-circ g $ を表す新しい関数を返します。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="ac3bf-108">入力</span><span class="sxs-lookup"><span data-stu-id="ac3bf-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="ac3bf-109">外部: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="ac3bf-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="ac3bf-110">適用する2番目の関数。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="ac3bf-111">内部: > ' U</span><span class="sxs-lookup"><span data-stu-id="ac3bf-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="ac3bf-112">適用される最初の関数。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="ac3bf-113">出力: > ' V</span><span class="sxs-lookup"><span data-stu-id="ac3bf-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="ac3bf-114">$、$F (g (x)) = h (x) $ のすべての入力 $x の新しい関数 $h $。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac3bf-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac3bf-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac3bf-116">&</span><span class="sxs-lookup"><span data-stu-id="ac3bf-116">'T</span></span>

<span data-ttu-id="ac3bf-117">適用する最初の関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="ac3bf-118">' U</span><span class="sxs-lookup"><span data-stu-id="ac3bf-118">'U</span></span>

<span data-ttu-id="ac3bf-119">適用される最初の関数の出力型と、適用する2番目の関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="ac3bf-120">' V</span><span class="sxs-lookup"><span data-stu-id="ac3bf-120">'V</span></span>

<span data-ttu-id="ac3bf-121">適用する2番目の関数の出力型。</span><span class="sxs-lookup"><span data-stu-id="ac3bf-121">The output type of the second function to be applied.</span></span>