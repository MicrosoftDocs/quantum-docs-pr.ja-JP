---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 2e39318cfaf3321c33b08f742bb25a9276b7e660
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196601"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="c0c9c-102">ApproximateInputEncoder 関数</span><span class="sxs-lookup"><span data-stu-id="c0c9c-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="c0c9c-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c0c9c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c0c9c-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c0c9c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c0c9c-105">係数と許容範囲が指定されている場合、は、指定された許容範囲に対して、計算ベース状態の対応する振幅として各係数を準備する状態準備操作を返します。</span><span class="sxs-lookup"><span data-stu-id="c0c9c-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="c0c9c-106">入力</span><span class="sxs-lookup"><span data-stu-id="c0c9c-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="c0c9c-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0c9c-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0c9c-108">指定された係数を入力状態にエンコードするときに使用される近似許容範囲。</span><span class="sxs-lookup"><span data-stu-id="c0c9c-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="c0c9c-109">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c0c9c-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c0c9c-110">入力状態にエンコードされる係数。</span><span class="sxs-lookup"><span data-stu-id="c0c9c-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="c0c9c-111">出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="c0c9c-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="c0c9c-112">指定された係数を特定のレジスタの入力状態として準備する状態準備操作。</span><span class="sxs-lookup"><span data-stu-id="c0c9c-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>