---
uid: Microsoft.Quantum.Intrinsic.Ry
title: 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720007"
---
# <a name="ry-operation"></a><span data-ttu-id="ef2e6-102">操作</span><span class="sxs-lookup"><span data-stu-id="ef2e6-102">Ry operation</span></span>

<span data-ttu-id="ef2e6-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ef2e6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ef2e6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef2e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef2e6-105">指定された角度で $y $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="ef2e6-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="ef2e6-106">\begin{align} R_y (-シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_y/2} = \begin{bmatrix}/cos \frac{\theta} {2} &-\ sin \frac{\theta}/ {2} \\ \\ sin \frac{\theta} {2} & \ cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="ef2e6-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="ef2e6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ef2e6-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ef2e6-108">入力</span><span class="sxs-lookup"><span data-stu-id="ef2e6-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="ef2e6-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ef2e6-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ef2e6-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="ef2e6-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ef2e6-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ef2e6-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ef2e6-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="ef2e6-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef2e6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef2e6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ef2e6-114">解説</span><span class="sxs-lookup"><span data-stu-id="ef2e6-114">Remarks</span></span>

<span data-ttu-id="ef2e6-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="ef2e6-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```