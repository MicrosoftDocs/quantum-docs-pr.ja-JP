---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204591"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="aa4dd-102">UncurriedOpC 関数</span><span class="sxs-lookup"><span data-stu-id="aa4dd-102">UncurriedOpC function</span></span>

<span data-ttu-id="aa4dd-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa4dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa4dd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa4dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa4dd-105">操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="aa4dd-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="aa4dd-107">入力</span><span class="sxs-lookup"><span data-stu-id="aa4dd-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="aa4dd-108">curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="aa4dd-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="aa4dd-109">操作を返す関数。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="aa4dd-110">出力: (' t '、' U) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl</span><span class="sxs-lookup"><span data-stu-id="aa4dd-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="aa4dd-111">と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa4dd-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa4dd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa4dd-113">&</span><span class="sxs-lookup"><span data-stu-id="aa4dd-113">'T</span></span>

<span data-ttu-id="aa4dd-114">カリー化関数の1番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="aa4dd-115">' U</span><span class="sxs-lookup"><span data-stu-id="aa4dd-115">'U</span></span>

<span data-ttu-id="aa4dd-116">カリー化関数の2番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="aa4dd-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa4dd-117">参照</span><span class="sxs-lookup"><span data-stu-id="aa4dd-117">See Also</span></span>

- [<span data-ttu-id="aa4dd-118">Microsoft... Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="aa4dd-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)