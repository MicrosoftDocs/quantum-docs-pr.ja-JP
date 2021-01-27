---
uid: Microsoft.Quantum.Canon.Compose
title: 関数の作成
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840902"
---
# <a name="compose-function"></a><span data-ttu-id="883a9-102">関数の作成</span><span class="sxs-lookup"><span data-stu-id="883a9-102">Compose function</span></span>

<span data-ttu-id="883a9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="883a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="883a9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="883a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="883a9-105">2つの関数の合成を返します。</span><span class="sxs-lookup"><span data-stu-id="883a9-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="883a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="883a9-106">Description</span></span>

<span data-ttu-id="883a9-107">$ および $g $ $f 2 つの関数が指定されている場合、$f-circ g $ を表す新しい関数を返します。</span><span class="sxs-lookup"><span data-stu-id="883a9-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="883a9-108">入力</span><span class="sxs-lookup"><span data-stu-id="883a9-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="883a9-109">外部: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="883a9-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="883a9-110">適用する2番目の関数。</span><span class="sxs-lookup"><span data-stu-id="883a9-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="883a9-111">内部: > ' U</span><span class="sxs-lookup"><span data-stu-id="883a9-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="883a9-112">適用される最初の関数。</span><span class="sxs-lookup"><span data-stu-id="883a9-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="883a9-113">出力: > ' V</span><span class="sxs-lookup"><span data-stu-id="883a9-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="883a9-114">$、$F (g (x)) = h (x) $ のすべての入力 $x の新しい関数 $h $。</span><span class="sxs-lookup"><span data-stu-id="883a9-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="883a9-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="883a9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="883a9-116">&</span><span class="sxs-lookup"><span data-stu-id="883a9-116">'T</span></span>

<span data-ttu-id="883a9-117">適用する最初の関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="883a9-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="883a9-118">' U</span><span class="sxs-lookup"><span data-stu-id="883a9-118">'U</span></span>

<span data-ttu-id="883a9-119">適用される最初の関数の出力型と、適用する2番目の関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="883a9-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="883a9-120">' V</span><span class="sxs-lookup"><span data-stu-id="883a9-120">'V</span></span>

<span data-ttu-id="883a9-121">適用する2番目の関数の出力型。</span><span class="sxs-lookup"><span data-stu-id="883a9-121">The output type of the second function to be applied.</span></span>