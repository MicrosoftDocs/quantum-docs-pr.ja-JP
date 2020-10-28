---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715687"
---
# <a name="operationpowc-function"></a><span data-ttu-id="dce04-102">OperationPowC 関数</span><span class="sxs-lookup"><span data-stu-id="dce04-102">OperationPowC function</span></span>

<span data-ttu-id="dce04-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dce04-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dce04-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dce04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dce04-105">操作を累乗します。</span><span class="sxs-lookup"><span data-stu-id="dce04-105">Raises an operation to a power.</span></span>
<span data-ttu-id="dce04-106">修飾子は、 `C` 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="dce04-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="dce04-107">つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="dce04-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="dce04-108">入力</span><span class="sxs-lookup"><span data-stu-id="dce04-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="dce04-109">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="dce04-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="dce04-110">繰り返すゲートを表す $ $U 演算。</span><span class="sxs-lookup"><span data-stu-id="dce04-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="dce04-111">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dce04-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dce04-112">$U $ を繰り返す回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="dce04-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="dce04-113">出力: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="dce04-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="dce04-114">$U ^ m $ を表す新しい操作 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="dce04-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dce04-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="dce04-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dce04-116">&</span><span class="sxs-lookup"><span data-stu-id="dce04-116">'T</span></span>

<span data-ttu-id="dce04-117">電力を供給する操作の種類。</span><span class="sxs-lookup"><span data-stu-id="dce04-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="dce04-118">参照</span><span class="sxs-lookup"><span data-stu-id="dce04-118">See Also</span></span>

- [<span data-ttu-id="dce04-119">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="dce04-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)