---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715211"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="04105-102">UncurriedOpC 関数</span><span class="sxs-lookup"><span data-stu-id="04105-102">UncurriedOpC function</span></span>

<span data-ttu-id="04105-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="04105-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="04105-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04105-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04105-105">操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="04105-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="04105-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="04105-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="04105-107">入力</span><span class="sxs-lookup"><span data-stu-id="04105-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="04105-108">curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="04105-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="04105-109">操作を返す関数。</span><span class="sxs-lookup"><span data-stu-id="04105-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="04105-110">出力: (' U '、' U) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="04105-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="04105-111">と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="04105-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="04105-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="04105-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04105-113">&</span><span class="sxs-lookup"><span data-stu-id="04105-113">'T</span></span>

<span data-ttu-id="04105-114">カリー化関数の1番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="04105-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="04105-115">' U</span><span class="sxs-lookup"><span data-stu-id="04105-115">'U</span></span>

<span data-ttu-id="04105-116">カリー化関数の2番目の引数の型。</span><span class="sxs-lookup"><span data-stu-id="04105-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="04105-117">参照</span><span class="sxs-lookup"><span data-stu-id="04105-117">See Also</span></span>

- [<span data-ttu-id="04105-118">Microsoft... Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="04105-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)