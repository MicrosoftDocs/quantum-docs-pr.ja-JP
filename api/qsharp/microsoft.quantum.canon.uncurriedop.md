---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204642"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="24f91-102">UncurriedOp 関数</span><span class="sxs-lookup"><span data-stu-id="24f91-102">UncurriedOp function</span></span>

<span data-ttu-id="24f91-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24f91-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24f91-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24f91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24f91-105">操作を返す関数を指定した場合、は、両方の入力をタプルとして受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="24f91-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="24f91-106">入力</span><span class="sxs-lookup"><span data-stu-id="24f91-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="24f91-107">curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24f91-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24f91-108">操作を返す関数。</span><span class="sxs-lookup"><span data-stu-id="24f91-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="24f91-109">出力: (' t, ' U) => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24f91-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24f91-110">と等価の新しい操作 `op` `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="24f91-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="24f91-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="24f91-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24f91-112">&</span><span class="sxs-lookup"><span data-stu-id="24f91-112">'T</span></span>

<span data-ttu-id="24f91-113">カリー化操作への最初の入力の型。</span><span class="sxs-lookup"><span data-stu-id="24f91-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="24f91-114">' U</span><span class="sxs-lookup"><span data-stu-id="24f91-114">'U</span></span>

<span data-ttu-id="24f91-115">カリー化操作への2番目の入力の型。</span><span class="sxs-lookup"><span data-stu-id="24f91-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="24f91-116">参照</span><span class="sxs-lookup"><span data-stu-id="24f91-116">See Also</span></span>

- [<span data-ttu-id="24f91-117">Microsoft. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="24f91-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="24f91-118">Microsoft. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="24f91-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="24f91-119">Microsoft. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="24f91-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)