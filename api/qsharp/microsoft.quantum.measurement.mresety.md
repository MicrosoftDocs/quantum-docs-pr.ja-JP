---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725010"
---
# <a name="mresety-operation"></a><span data-ttu-id="8313e-102">MResetY 操作</span><span class="sxs-lookup"><span data-stu-id="8313e-102">MResetY operation</span></span>

<span data-ttu-id="8313e-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8313e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8313e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8313e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8313e-105">Y 単位で1つの qubit を測定し、測定値に従って固定の初期状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="8313e-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="8313e-106">説明</span><span class="sxs-lookup"><span data-stu-id="8313e-106">Description</span></span>

<span data-ttu-id="8313e-107">$Y $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="8313e-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="8313e-108">入力</span><span class="sxs-lookup"><span data-stu-id="8313e-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8313e-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8313e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8313e-110">測定される1つの qubit。</span><span class="sxs-lookup"><span data-stu-id="8313e-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8313e-111">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="8313e-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8313e-112">`target`P# li $Y $ ベースで測定した結果。</span><span class="sxs-lookup"><span data-stu-id="8313e-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>