---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: 乗数 Yfxp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222611"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="cf1c4-102">乗数 Yfxp 操作</span><span class="sxs-lookup"><span data-stu-id="cf1c4-102">MultiplyFxP operation</span></span>

<span data-ttu-id="cf1c4-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cf1c4-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cf1c4-105">クォンタムレジスタの2つの固定小数点数を乗算します。</span><span class="sxs-lookup"><span data-stu-id="cf1c4-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cf1c4-106">入力</span><span class="sxs-lookup"><span data-stu-id="cf1c4-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="cf1c4-107">fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf1c4-108">最初の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="cf1c4-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="cf1c4-109">fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf1c4-110">2番目の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="cf1c4-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="cf1c4-111">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf1c4-112">結果の固定小数点数は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="cf1c4-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf1c4-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf1c4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cf1c4-114">解説</span><span class="sxs-lookup"><span data-stu-id="cf1c4-114">Remarks</span></span>

<span data-ttu-id="cf1c4-115">現在の実装では、3つの固定小数点数が同じポイント位置と同じ数の qubits を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1c4-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>