---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222407"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="d973e-102">PrepareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="d973e-102">PrepareFxP operation</span></span>

<span data-ttu-id="d973e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d973e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d973e-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d973e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d973e-105">クォンタム固定小数点数を古典定数に初期化します。</span><span class="sxs-lookup"><span data-stu-id="d973e-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d973e-106">入力</span><span class="sxs-lookup"><span data-stu-id="d973e-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="d973e-107">定数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d973e-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d973e-108">クォンタム固定小数点数を初期化する定数。</span><span class="sxs-lookup"><span data-stu-id="d973e-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="d973e-109">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d973e-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d973e-110">初期化する固定小数点数 (型 FixedPoint)。</span><span class="sxs-lookup"><span data-stu-id="d973e-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d973e-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d973e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

