---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716368"
---
# <a name="curriedop-function"></a><span data-ttu-id="6a8d3-102">CurriedOp 関数</span><span class="sxs-lookup"><span data-stu-id="6a8d3-102">CurriedOp function</span></span>

<span data-ttu-id="6a8d3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a8d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a8d3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a8d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a8d3-105">2つの入力に対して、カリー化された操作のバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="6a8d3-106">つまり、2つの入力を持つ演算が指定された場合、この関数は、isomorphism $f (x, y) \equiv f (x) (y) $ という値を適用して、1つの入力の操作を返す1つの入力の操作を返します。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="6a8d3-107">入力</span><span class="sxs-lookup"><span data-stu-id="6a8d3-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="6a8d3-108">op: (' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a8d3-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6a8d3-109">入力がペアである操作。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="6a8d3-110">出力: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a8d3-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6a8d3-111">ペアの最初の要素を受け取り、元の操作の入力の2番目の要素を入力として受け入れる演算を返す操作。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6a8d3-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a8d3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a8d3-113">&</span><span class="sxs-lookup"><span data-stu-id="6a8d3-113">'T</span></span>

<span data-ttu-id="6a8d3-114">ペアで定義された関数の最初のコンポーネントの型。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="6a8d3-115">' U</span><span class="sxs-lookup"><span data-stu-id="6a8d3-115">'U</span></span>

<span data-ttu-id="6a8d3-116">ペアで定義された関数の2番目のコンポーネントの型。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a8d3-117">解説</span><span class="sxs-lookup"><span data-stu-id="6a8d3-117">Remarks</span></span>

<span data-ttu-id="6a8d3-118">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a8d3-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```