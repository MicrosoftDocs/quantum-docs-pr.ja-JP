---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725001"
---
# <a name="mresetx-operation"></a><span data-ttu-id="cb6d5-102">MResetX 操作</span><span class="sxs-lookup"><span data-stu-id="cb6d5-102">MResetX operation</span></span>

<span data-ttu-id="cb6d5-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="cb6d5-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="cb6d5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb6d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb6d5-105">X ベースの1つの qubit を測定し、測定値に従って固定の初期状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="cb6d5-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="cb6d5-106">説明</span><span class="sxs-lookup"><span data-stu-id="cb6d5-106">Description</span></span>

<span data-ttu-id="cb6d5-107">$X $ 単位で1つの qubit 測定を実行し、測定値に従って qubit が $ \ket $ に返されることを確認し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="cb6d5-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="cb6d5-108">入力</span><span class="sxs-lookup"><span data-stu-id="cb6d5-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="cb6d5-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb6d5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb6d5-110">測定される1つの qubit。</span><span class="sxs-lookup"><span data-stu-id="cb6d5-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="cb6d5-111">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="cb6d5-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="cb6d5-112">`target`P# li $X $ ベースで測定した結果。</span><span class="sxs-lookup"><span data-stu-id="cb6d5-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>