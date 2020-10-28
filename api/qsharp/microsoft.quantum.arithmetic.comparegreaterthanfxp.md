---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721298"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="078e9-102">CompareGreaterThanFxP 操作</span><span class="sxs-lookup"><span data-stu-id="078e9-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="078e9-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="078e9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="078e9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="078e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="078e9-105">クォンタムレジスタに格納されている2つの固定小数点数を比較し、結果のフリップを制御します。</span><span class="sxs-lookup"><span data-stu-id="078e9-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="078e9-106">入力</span><span class="sxs-lookup"><span data-stu-id="078e9-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="078e9-107">fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="078e9-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="078e9-108">比較する最初の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="078e9-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="078e9-109">fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="078e9-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="078e9-110">比較する2番目の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="078e9-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="078e9-111">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="078e9-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="078e9-112">比較の結果。</span><span class="sxs-lookup"><span data-stu-id="078e9-112">Result of the comparison.</span></span> <span data-ttu-id="078e9-113">は、の場合には反転され `fp1 > fp2` ます。</span><span class="sxs-lookup"><span data-stu-id="078e9-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="078e9-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="078e9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="078e9-115">解説</span><span class="sxs-lookup"><span data-stu-id="078e9-115">Remarks</span></span>

<span data-ttu-id="078e9-116">現在の実装では、2つの固定小数点数が同じポイント位置と同じ数の qubits を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="078e9-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>