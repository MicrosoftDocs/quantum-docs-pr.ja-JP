---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720931"
---
# <a name="r-operation"></a><span data-ttu-id="33dd8-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="33dd8-102">R operation</span></span>

<span data-ttu-id="33dd8-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="33dd8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="33dd8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33dd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33dd8-105">指定された P# li 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="33dd8-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="33dd8-106">\begin{align} R_ {\ mu} (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_ {/mu}/2}、\end{align} where $ \ mu \ \{ i, X, Y, Z \} $ です。</span><span class="sxs-lookup"><span data-stu-id="33dd8-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="33dd8-107">入力</span><span class="sxs-lookup"><span data-stu-id="33dd8-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="33dd8-108">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="33dd8-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="33dd8-109">回転を形成するために累乗される p# li 演算子 ($ \ mu $)。</span><span class="sxs-lookup"><span data-stu-id="33dd8-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="33dd8-110">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33dd8-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33dd8-111">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="33dd8-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="33dd8-112">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33dd8-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33dd8-113">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="33dd8-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33dd8-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33dd8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33dd8-115">解説</span><span class="sxs-lookup"><span data-stu-id="33dd8-115">Remarks</span></span>

<span data-ttu-id="33dd8-116">で呼び出された場合 `pauli = PauliI` 、この操作は *グローバルフェーズ* を適用します。</span><span class="sxs-lookup"><span data-stu-id="33dd8-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="33dd8-117">このフェーズは、ファンクタで使用する場合に重要になり `Controlled` ます。</span><span class="sxs-lookup"><span data-stu-id="33dd8-117">This phase can be significant when used with the `Controlled` functor.</span></span>