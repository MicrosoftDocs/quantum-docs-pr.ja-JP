---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 31ed1a170a47c77c21aa8b5c291860e422af2e3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845795"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="0e3c0-102">PrepareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="0e3c0-102">PrepareFxP operation</span></span>

<span data-ttu-id="0e3c0-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0e3c0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0e3c0-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0e3c0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0e3c0-105">クォンタム固定小数点数を古典定数に初期化します。</span><span class="sxs-lookup"><span data-stu-id="0e3c0-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e3c0-106">入力</span><span class="sxs-lookup"><span data-stu-id="0e3c0-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="0e3c0-107">定数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e3c0-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e3c0-108">クォンタム固定小数点数を初期化する定数。</span><span class="sxs-lookup"><span data-stu-id="0e3c0-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="0e3c0-109">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0e3c0-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0e3c0-110">初期化する固定小数点数 (型 FixedPoint)。</span><span class="sxs-lookup"><span data-stu-id="0e3c0-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e3c0-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e3c0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

