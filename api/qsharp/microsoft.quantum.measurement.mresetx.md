---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853756"
---
# <a name="mresetx-operation"></a><span data-ttu-id="3b404-102">MResetX 操作</span><span class="sxs-lookup"><span data-stu-id="3b404-102">MResetX operation</span></span>

<span data-ttu-id="3b404-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3b404-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3b404-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3b404-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b404-105">X ベースの1つの qubit を測定し、測定値に従って固定の初期状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="3b404-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="3b404-106">説明</span><span class="sxs-lookup"><span data-stu-id="3b404-106">Description</span></span>

<span data-ttu-id="3b404-107">$X $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="3b404-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="3b404-108">入力</span><span class="sxs-lookup"><span data-stu-id="3b404-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="3b404-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b404-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b404-110">測定される1つの qubit。</span><span class="sxs-lookup"><span data-stu-id="3b404-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3b404-111">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3b404-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="3b404-112">`target`P# li $X $ ベースで測定した結果。</span><span class="sxs-lookup"><span data-stu-id="3b404-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>