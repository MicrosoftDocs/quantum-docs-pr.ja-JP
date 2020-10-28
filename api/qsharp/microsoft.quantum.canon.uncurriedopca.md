---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715206"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="bfb99-102">UncurriedOpCA 関数</span><span class="sxs-lookup"><span data-stu-id="bfb99-102">UncurriedOpCA function</span></span>

<span data-ttu-id="bfb99-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfb99-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfb99-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfb99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfb99-105">操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="bfb99-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="bfb99-106">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="bfb99-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="bfb99-107">入力</span><span class="sxs-lookup"><span data-stu-id="bfb99-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="bfb99-108">curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="bfb99-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="bfb99-109">操作を返す関数。</span><span class="sxs-lookup"><span data-stu-id="bfb99-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="bfb99-110">出力: (' t '、' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="bfb99-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="bfb99-111">と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="bfb99-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bfb99-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfb99-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfb99-113">&</span><span class="sxs-lookup"><span data-stu-id="bfb99-113">'T</span></span>

<span data-ttu-id="bfb99-114">カリー化関数の1番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="bfb99-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="bfb99-115">' U</span><span class="sxs-lookup"><span data-stu-id="bfb99-115">'U</span></span>

<span data-ttu-id="bfb99-116">カリー化関数の2番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="bfb99-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfb99-117">参照</span><span class="sxs-lookup"><span data-stu-id="bfb99-117">See Also</span></span>

- [<span data-ttu-id="bfb99-118">Microsoft... Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="bfb99-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)