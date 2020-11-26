---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: eb2dd8750ed5ad9fc75ca24bb4c8ef36298f69f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198777"
---
# <a name="r1frac-operation"></a><span data-ttu-id="8700a-102">R1Frac 操作</span><span class="sxs-lookup"><span data-stu-id="8700a-102">R1Frac operation</span></span>

<span data-ttu-id="8700a-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8700a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8700a-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="8700a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8700a-105">{1}Dyadic の割合として指定された角度で、$ \ket $ 状態に関する回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="8700a-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="8700a-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \ pi k/2 ^ n})。</span><span class="sxs-lookup"><span data-stu-id="8700a-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="8700a-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8700a-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="8700a-108">この操作では、とは **逆** の符号規則を使用 @"microsoft.quantum.intrinsic.r" し、に含まれる $ 1/2 $ の係数は含まれません @"microsoft.quantum.intrinsic.r1" 。</span><span class="sxs-lookup"><span data-stu-id="8700a-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8700a-109">入力</span><span class="sxs-lookup"><span data-stu-id="8700a-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="8700a-110">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8700a-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8700a-111">Qubit を回転する角度の、dyadic の分数表現の分子。</span><span class="sxs-lookup"><span data-stu-id="8700a-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="8700a-112">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8700a-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8700a-113">Qubit を回転する角度の分母を指定する2の累乗。</span><span class="sxs-lookup"><span data-stu-id="8700a-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="8700a-114">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8700a-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8700a-115">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="8700a-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8700a-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8700a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8700a-117">解説</span><span class="sxs-lookup"><span data-stu-id="8700a-117">Remarks</span></span>

<span data-ttu-id="8700a-118">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="8700a-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```