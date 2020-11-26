---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199031"
---
# <a name="r-operation"></a><span data-ttu-id="939b0-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="939b0-102">R operation</span></span>

<span data-ttu-id="939b0-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="939b0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="939b0-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="939b0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="939b0-105">指定された P# li 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="939b0-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="939b0-106">\begin{align} R_ {\ mu} (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_ {/mu}/2}、\end{align} where $ \ mu \ \{ i, X, Y, Z \} $ です。</span><span class="sxs-lookup"><span data-stu-id="939b0-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="939b0-107">入力</span><span class="sxs-lookup"><span data-stu-id="939b0-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="939b0-108">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="939b0-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="939b0-109">回転を形成するために累乗される p# li 演算子 ($ \ mu $)。</span><span class="sxs-lookup"><span data-stu-id="939b0-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="939b0-110">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="939b0-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="939b0-111">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="939b0-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="939b0-112">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="939b0-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="939b0-113">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="939b0-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="939b0-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="939b0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="939b0-115">解説</span><span class="sxs-lookup"><span data-stu-id="939b0-115">Remarks</span></span>

<span data-ttu-id="939b0-116">で呼び出された場合 `pauli = PauliI` 、この操作は *グローバルフェーズ* を適用します。</span><span class="sxs-lookup"><span data-stu-id="939b0-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="939b0-117">このフェーズは、ファンクタで使用する場合に重要になり `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="939b0-117">This phase can be significant when used with the `Controlled` functor.</span></span>