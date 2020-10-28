---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720919"
---
# <a name="r1-operation"></a><span data-ttu-id="e8408-102">R1 操作</span><span class="sxs-lookup"><span data-stu-id="e8408-102">R1 operation</span></span>

<span data-ttu-id="e8408-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e8408-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e8408-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8408-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8408-105">$ \Ket $ 状態に関する回転を {1} 、指定された角度で適用します。</span><span class="sxs-lookup"><span data-stu-id="e8408-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="e8408-106">\begin{align} R_1 (\ シータ) \mathrel{: =} \operatorname{diag} (1, e ^ {i\ シータ})。</span><span class="sxs-lookup"><span data-stu-id="e8408-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="e8408-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e8408-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e8408-108">入力</span><span class="sxs-lookup"><span data-stu-id="e8408-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="e8408-109">シータ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8408-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8408-110">Qubit を回転する角度。</span><span class="sxs-lookup"><span data-stu-id="e8408-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e8408-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8408-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8408-112">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="e8408-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8408-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8408-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8408-114">解説</span><span class="sxs-lookup"><span data-stu-id="e8408-114">Remarks</span></span>

<span data-ttu-id="e8408-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="e8408-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```