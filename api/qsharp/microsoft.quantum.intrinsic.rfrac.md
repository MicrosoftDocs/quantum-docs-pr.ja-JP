---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723512"
---
# <a name="rfrac-operation"></a><span data-ttu-id="44cbc-102">RFrac 操作</span><span class="sxs-lookup"><span data-stu-id="44cbc-102">RFrac operation</span></span>

<span data-ttu-id="44cbc-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="44cbc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="44cbc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44cbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44cbc-105">指定された P# li 軸に関する回転を、dyadic の分数として指定された角度だけ適用します。</span><span class="sxs-lookup"><span data-stu-id="44cbc-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="44cbc-106">\begin{align} R_ {\ mu} (n, k) \mathrel{: =} e ^ {i \ pi n \ sigma_ {/mu}/2 ^ k}、\end{align} where $ \ mu \ in \{ i, X, Y, Z \} $ です。</span><span class="sxs-lookup"><span data-stu-id="44cbc-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="44cbc-107">この操作では、とは **逆** の符号規則を使用 @"microsoft.quantum.intrinsic.r" します。</span><span class="sxs-lookup"><span data-stu-id="44cbc-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="44cbc-108">入力</span><span class="sxs-lookup"><span data-stu-id="44cbc-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="44cbc-109">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="44cbc-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="44cbc-110">回転を形成するために累乗する p# li 演算子。</span><span class="sxs-lookup"><span data-stu-id="44cbc-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="44cbc-111">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44cbc-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44cbc-112">Qubit を回転する角度の、dyadic の分数表現の分子。</span><span class="sxs-lookup"><span data-stu-id="44cbc-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="44cbc-113">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44cbc-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44cbc-114">Qubit を回転する角度の分母を指定する2の累乗。</span><span class="sxs-lookup"><span data-stu-id="44cbc-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="44cbc-115">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="44cbc-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="44cbc-116">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="44cbc-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44cbc-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44cbc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="44cbc-118">解説</span><span class="sxs-lookup"><span data-stu-id="44cbc-118">Remarks</span></span>

<span data-ttu-id="44cbc-119">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="44cbc-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```