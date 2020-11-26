---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198641"
---
# <a name="rfrac-operation"></a><span data-ttu-id="59797-102">RFrac 操作</span><span class="sxs-lookup"><span data-stu-id="59797-102">RFrac operation</span></span>

<span data-ttu-id="59797-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="59797-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="59797-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="59797-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="59797-105">指定された P# li 軸に関する回転を、dyadic の分数として指定された角度だけ適用します。</span><span class="sxs-lookup"><span data-stu-id="59797-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="59797-106">\begin{align} R_ {\ mu} (n, k) \mathrel{: =} e ^ {i \ pi n \ sigma_ {/mu}/2 ^ k}、\end{align} where $ \ mu \ in \{ i, X, Y, Z \} $ です。</span><span class="sxs-lookup"><span data-stu-id="59797-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="59797-107">この操作では、とは **逆** の符号規則を使用 @"microsoft.quantum.intrinsic.r" します。</span><span class="sxs-lookup"><span data-stu-id="59797-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="59797-108">入力</span><span class="sxs-lookup"><span data-stu-id="59797-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="59797-109">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="59797-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="59797-110">回転を形成するために累乗する p# li 演算子。</span><span class="sxs-lookup"><span data-stu-id="59797-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="59797-111">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59797-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59797-112">Qubit を回転する角度の、dyadic の分数表現の分子。</span><span class="sxs-lookup"><span data-stu-id="59797-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="59797-113">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59797-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59797-114">Qubit を回転する角度の分母を指定する2の累乗。</span><span class="sxs-lookup"><span data-stu-id="59797-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="59797-115">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="59797-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="59797-116">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="59797-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59797-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59797-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="59797-118">解説</span><span class="sxs-lookup"><span data-stu-id="59797-118">Remarks</span></span>

<span data-ttu-id="59797-119">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="59797-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```