---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: 8d08cb51e3a7ae892b23be0adbb7cdf3ee0f4de5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221880"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="39b46-102">SquareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="39b46-102">SquareFxP operation</span></span>

<span data-ttu-id="39b46-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39b46-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39b46-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="39b46-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="39b46-105">は固定小数点数を二乗します。</span><span class="sxs-lookup"><span data-stu-id="39b46-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="39b46-106">入力</span><span class="sxs-lookup"><span data-stu-id="39b46-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="39b46-107">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="39b46-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="39b46-108">固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="39b46-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="39b46-109">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="39b46-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="39b46-110">結果の固定小数点数は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="39b46-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39b46-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39b46-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

