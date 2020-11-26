---
uid: Microsoft.Quantum.Intrinsic.Z
title: Z 演算
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Z
qsharp.summary: >-
  Applies the Pauli $Z$ gate.

  \begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 5bfb435a1e7a7b90da807e7c6edb8358fb006e34
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198437"
---
# <a name="z-operation"></a><span data-ttu-id="78947-102">Z 演算</span><span class="sxs-lookup"><span data-stu-id="78947-102">Z operation</span></span>

<span data-ttu-id="78947-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="78947-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="78947-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="78947-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="78947-105">P# li $Z $ gate を適用します。</span><span class="sxs-lookup"><span data-stu-id="78947-105">Applies the Pauli $Z$ gate.</span></span>

<span data-ttu-id="78947-106">\begin{align} \ sigma_z \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="78947-106">\begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="78947-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="78947-107">\end{align}</span></span>

```qsharp
operation Z (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78947-108">入力</span><span class="sxs-lookup"><span data-stu-id="78947-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="78947-109">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78947-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78947-110">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="78947-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78947-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78947-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

