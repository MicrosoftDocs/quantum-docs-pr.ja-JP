---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723503"
---
# <a name="rx-operation"></a><span data-ttu-id="5bf11-102">Rx 操作</span><span class="sxs-lookup"><span data-stu-id="5bf11-102">Rx operation</span></span>

<span data-ttu-id="5bf11-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5bf11-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5bf11-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bf11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bf11-105">指定された角度で $x $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="5bf11-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="5bf11-106">\begin{align} R_x (-シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_x/2} = \begin{bmatrix}/cos \frac{\theta} {2} &-i\ sin \frac{\theta} {2} \\ \\ -i\ sin \frac{\theta} {2} & \ cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="5bf11-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="5bf11-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5bf11-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5bf11-108">入力</span><span class="sxs-lookup"><span data-stu-id="5bf11-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="5bf11-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5bf11-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5bf11-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="5bf11-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5bf11-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5bf11-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5bf11-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="5bf11-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bf11-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bf11-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5bf11-114">解説</span><span class="sxs-lookup"><span data-stu-id="5bf11-114">Remarks</span></span>

<span data-ttu-id="5bf11-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bf11-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```