---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853738"
---
# <a name="mresetz-operation"></a><span data-ttu-id="6c06b-102">MResetZ 操作</span><span class="sxs-lookup"><span data-stu-id="6c06b-102">MResetZ operation</span></span>

<span data-ttu-id="6c06b-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6c06b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6c06b-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="6c06b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6c06b-105">1つの qubit を Z ベースで測定し、測定値に従って固定の初期状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="6c06b-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="6c06b-106">説明</span><span class="sxs-lookup"><span data-stu-id="6c06b-106">Description</span></span>

<span data-ttu-id="6c06b-107">$Z $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="6c06b-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="6c06b-108">入力</span><span class="sxs-lookup"><span data-stu-id="6c06b-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="6c06b-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6c06b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6c06b-110">測定される1つの qubit。</span><span class="sxs-lookup"><span data-stu-id="6c06b-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6c06b-111">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6c06b-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6c06b-112">`target`P# li $Z $ ベースで測定した結果。</span><span class="sxs-lookup"><span data-stu-id="6c06b-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>