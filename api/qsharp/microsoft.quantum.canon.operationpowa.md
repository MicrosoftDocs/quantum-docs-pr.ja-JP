---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715715"
---
# <a name="operationpowa-function"></a><span data-ttu-id="3acbf-102">OperationPowA 関数</span><span class="sxs-lookup"><span data-stu-id="3acbf-102">OperationPowA function</span></span>

<span data-ttu-id="3acbf-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3acbf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3acbf-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3acbf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3acbf-105">操作を累乗します。</span><span class="sxs-lookup"><span data-stu-id="3acbf-105">Raises an operation to a power.</span></span>
<span data-ttu-id="3acbf-106">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="3acbf-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="3acbf-107">つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="3acbf-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3acbf-108">入力</span><span class="sxs-lookup"><span data-stu-id="3acbf-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="3acbf-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="3acbf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3acbf-110">繰り返すゲートを表す $ $U 演算。</span><span class="sxs-lookup"><span data-stu-id="3acbf-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="3acbf-111">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3acbf-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3acbf-112">$U $ を繰り返す回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3acbf-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="3acbf-113">出力: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="3acbf-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3acbf-114">$U ^ m $ を表す新しい操作 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="3acbf-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3acbf-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3acbf-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3acbf-116">&</span><span class="sxs-lookup"><span data-stu-id="3acbf-116">'T</span></span>

<span data-ttu-id="3acbf-117">電力を供給する操作の種類。</span><span class="sxs-lookup"><span data-stu-id="3acbf-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="3acbf-118">参照</span><span class="sxs-lookup"><span data-stu-id="3acbf-118">See Also</span></span>

- [<span data-ttu-id="3acbf-119">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="3acbf-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)