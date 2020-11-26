---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204625"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="397f0-102">UncurriedOpA 関数</span><span class="sxs-lookup"><span data-stu-id="397f0-102">UncurriedOpA function</span></span>

<span data-ttu-id="397f0-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="397f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="397f0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="397f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="397f0-105">操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="397f0-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="397f0-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="397f0-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="397f0-107">入力</span><span class="sxs-lookup"><span data-stu-id="397f0-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="397f0-108">curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="397f0-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="397f0-109">操作を返す関数。</span><span class="sxs-lookup"><span data-stu-id="397f0-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="397f0-110">出力: (' t, ' U) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞</span><span class="sxs-lookup"><span data-stu-id="397f0-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="397f0-111">と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="397f0-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="397f0-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="397f0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="397f0-113">&</span><span class="sxs-lookup"><span data-stu-id="397f0-113">'T</span></span>

<span data-ttu-id="397f0-114">カリー化関数の1番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="397f0-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="397f0-115">' U</span><span class="sxs-lookup"><span data-stu-id="397f0-115">'U</span></span>

<span data-ttu-id="397f0-116">カリー化関数の2番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="397f0-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="397f0-117">参照</span><span class="sxs-lookup"><span data-stu-id="397f0-117">See Also</span></span>

- [<span data-ttu-id="397f0-118">Microsoft... Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="397f0-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)