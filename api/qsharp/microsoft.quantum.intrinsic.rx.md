---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 49638c00967ff2f47dad41acfed05868d65a24a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198590"
---
# <a name="rx-operation"></a><span data-ttu-id="39e53-102">Rx 操作</span><span class="sxs-lookup"><span data-stu-id="39e53-102">Rx operation</span></span>

<span data-ttu-id="39e53-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="39e53-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="39e53-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="39e53-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="39e53-105">指定された角度で $x $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="39e53-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="39e53-106">\begin{align} R_x (-シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_x/2} = \begin{bmatrix}/cos \frac{\theta} {2} &-i\ sin \frac{\theta} {2} \\ \\ -i\ sin \frac{\theta} {2} & \ cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="39e53-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="39e53-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="39e53-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="39e53-108">入力</span><span class="sxs-lookup"><span data-stu-id="39e53-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="39e53-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="39e53-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="39e53-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="39e53-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="39e53-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="39e53-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="39e53-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="39e53-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39e53-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39e53-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39e53-114">解説</span><span class="sxs-lookup"><span data-stu-id="39e53-114">Remarks</span></span>

<span data-ttu-id="39e53-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="39e53-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```