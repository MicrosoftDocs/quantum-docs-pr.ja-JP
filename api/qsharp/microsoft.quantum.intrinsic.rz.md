---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Rz 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720866"
---
# <a name="rz-operation"></a><span data-ttu-id="0bca1-102">Rz 操作</span><span class="sxs-lookup"><span data-stu-id="0bca1-102">Rz operation</span></span>

<span data-ttu-id="0bca1-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0bca1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0bca1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bca1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bca1-105">指定された角度で $z $ 軸についての回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="0bca1-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="0bca1-106">\begin{align} R_z (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_z/2} = \begin{bmatrix} e ^ {-i \ シータ/2} & 0 \\ \\ 0 & e ^ {i/シータ/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="0bca1-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="0bca1-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0bca1-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0bca1-108">入力</span><span class="sxs-lookup"><span data-stu-id="0bca1-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="0bca1-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0bca1-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0bca1-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="0bca1-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0bca1-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0bca1-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0bca1-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="0bca1-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bca1-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bca1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0bca1-114">解説</span><span class="sxs-lookup"><span data-stu-id="0bca1-114">Remarks</span></span>

<span data-ttu-id="0bca1-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="0bca1-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```