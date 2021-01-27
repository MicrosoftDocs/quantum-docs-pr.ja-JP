---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852304"
---
# <a name="operationpowca-function"></a><span data-ttu-id="b5528-102">OperationPowCA 関数</span><span class="sxs-lookup"><span data-stu-id="b5528-102">OperationPowCA function</span></span>

<span data-ttu-id="b5528-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5528-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5528-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5528-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5528-105">操作を累乗します。</span><span class="sxs-lookup"><span data-stu-id="b5528-105">Raises an operation to a power.</span></span>
<span data-ttu-id="b5528-106">修飾子は、 `A` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b5528-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="b5528-107">つまり、ゲート $U $ を表す操作が指定されている場合は、power $m $ に対して ^ m $ $U 新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b5528-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="b5528-108">入力</span><span class="sxs-lookup"><span data-stu-id="b5528-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b5528-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="b5528-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b5528-110">繰り返すゲートを表す $ $U 演算。</span><span class="sxs-lookup"><span data-stu-id="b5528-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="b5528-111">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5528-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5528-112">$U $ を繰り返す回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5528-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="b5528-113">出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="b5528-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b5528-114">$U ^ m $ を表す新しい操作 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="b5528-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5528-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5528-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5528-116">&</span><span class="sxs-lookup"><span data-stu-id="b5528-116">'T</span></span>

<span data-ttu-id="b5528-117">電力を供給する操作の種類。</span><span class="sxs-lookup"><span data-stu-id="b5528-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5528-118">参照</span><span class="sxs-lookup"><span data-stu-id="b5528-118">See Also</span></span>

- [<span data-ttu-id="b5528-119">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="b5528-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)