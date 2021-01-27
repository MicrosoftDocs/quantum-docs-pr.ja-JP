---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852376"
---
# <a name="operationpow-function"></a><span data-ttu-id="3e5a1-102">OperationPow 関数</span><span class="sxs-lookup"><span data-stu-id="3e5a1-102">OperationPow function</span></span>

<span data-ttu-id="3e5a1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e5a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e5a1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e5a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e5a1-105">操作を累乗します。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-105">Raises an operation to a power.</span></span>

<span data-ttu-id="3e5a1-106">つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="3e5a1-107">入力</span><span class="sxs-lookup"><span data-stu-id="3e5a1-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="3e5a1-108">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e5a1-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3e5a1-109">繰り返すゲートを表す $ $U 演算。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="3e5a1-110">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e5a1-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e5a1-111">$U $ を繰り返す回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="3e5a1-112">出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e5a1-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3e5a1-113">$U ^ m $ を表す新しい操作 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3e5a1-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e5a1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3e5a1-115">&</span><span class="sxs-lookup"><span data-stu-id="3e5a1-115">'T</span></span>

<span data-ttu-id="3e5a1-116">電力を供給する操作の種類。</span><span class="sxs-lookup"><span data-stu-id="3e5a1-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e5a1-117">参照</span><span class="sxs-lookup"><span data-stu-id="3e5a1-117">See Also</span></span>

- [<span data-ttu-id="3e5a1-118">Microsoft. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="3e5a1-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="3e5a1-119">Microsoft. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="3e5a1-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="3e5a1-120">Microsoft. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="3e5a1-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)