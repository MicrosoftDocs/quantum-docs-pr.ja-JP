---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Rz 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198624"
---
# <a name="rz-operation"></a><span data-ttu-id="e9f9b-102">Rz 操作</span><span class="sxs-lookup"><span data-stu-id="e9f9b-102">Rz operation</span></span>

<span data-ttu-id="e9f9b-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e9f9b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e9f9b-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="e9f9b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e9f9b-105">指定された角度で $z $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="e9f9b-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="e9f9b-106">\begin{align} R_z (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_z/2} = \begin{bmatrix} e ^ {-i \ シータ/2} & 0 \\ \\ 0 & e ^ {i/シータ/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="e9f9b-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="e9f9b-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e9f9b-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9f9b-108">入力</span><span class="sxs-lookup"><span data-stu-id="e9f9b-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="e9f9b-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9f9b-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9f9b-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="e9f9b-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e9f9b-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e9f9b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e9f9b-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="e9f9b-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9f9b-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9f9b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e9f9b-114">解説</span><span class="sxs-lookup"><span data-stu-id="e9f9b-114">Remarks</span></span>

<span data-ttu-id="e9f9b-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="e9f9b-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```