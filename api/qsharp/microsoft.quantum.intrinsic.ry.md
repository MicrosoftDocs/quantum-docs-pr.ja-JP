---
uid: Microsoft.Quantum.Intrinsic.Ry
title: 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818279"
---
# <a name="ry-operation"></a><span data-ttu-id="60e20-102">操作</span><span class="sxs-lookup"><span data-stu-id="60e20-102">Ry operation</span></span>

<span data-ttu-id="60e20-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="60e20-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="60e20-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="60e20-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="60e20-105">指定された角度で $y $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="60e20-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="60e20-106">\begin{align} R_y (-シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_y/2} = \begin{bmatrix}/cos \frac{\theta} {2} &-\ sin \frac{\theta}/ {2} \\ \\ sin \frac{\theta} {2} & \ cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="60e20-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="60e20-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="60e20-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="60e20-108">入力</span><span class="sxs-lookup"><span data-stu-id="60e20-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="60e20-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60e20-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="60e20-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="60e20-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="60e20-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="60e20-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="60e20-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="60e20-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60e20-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60e20-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="60e20-114">解説</span><span class="sxs-lookup"><span data-stu-id="60e20-114">Remarks</span></span>

<span data-ttu-id="60e20-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="60e20-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```