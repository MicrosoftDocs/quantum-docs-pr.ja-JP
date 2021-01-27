---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842913"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="da4d3-102">SquareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="da4d3-102">SquareFxP operation</span></span>

<span data-ttu-id="da4d3-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="da4d3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="da4d3-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="da4d3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="da4d3-105">は固定小数点数を二乗します。</span><span class="sxs-lookup"><span data-stu-id="da4d3-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da4d3-106">入力</span><span class="sxs-lookup"><span data-stu-id="da4d3-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="da4d3-107">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="da4d3-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="da4d3-108">固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="da4d3-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="da4d3-109">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="da4d3-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="da4d3-110">結果の固定小数点数は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="da4d3-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da4d3-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da4d3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

