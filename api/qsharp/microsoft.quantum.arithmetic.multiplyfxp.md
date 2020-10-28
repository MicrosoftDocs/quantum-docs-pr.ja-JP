---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: 乗数 Yfxp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719779"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="aa1e6-102">乗数 Yfxp 操作</span><span class="sxs-lookup"><span data-stu-id="aa1e6-102">MultiplyFxP operation</span></span>

<span data-ttu-id="aa1e6-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa1e6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa1e6-105">クォンタムレジスタの2つの固定小数点数を乗算します。</span><span class="sxs-lookup"><span data-stu-id="aa1e6-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="aa1e6-106">入力</span><span class="sxs-lookup"><span data-stu-id="aa1e6-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="aa1e6-107">fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="aa1e6-108">最初の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="aa1e6-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="aa1e6-109">fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="aa1e6-110">2番目の固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="aa1e6-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="aa1e6-111">結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="aa1e6-112">結果の固定小数点数は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="aa1e6-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa1e6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa1e6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa1e6-114">解説</span><span class="sxs-lookup"><span data-stu-id="aa1e6-114">Remarks</span></span>

<span data-ttu-id="aa1e6-115">現在の実装では、3つの固定小数点数が同じポイント位置と同じ数の qubits を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa1e6-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>