---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720535"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="9ad5d-102">ApproximateInputEncoder 関数</span><span class="sxs-lookup"><span data-stu-id="9ad5d-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="9ad5d-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9ad5d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9ad5d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ad5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ad5d-105">係数と許容範囲が指定されている場合、は、指定された許容範囲に対して、計算ベース状態の対応する振幅として各係数を準備する状態準備操作を返します。</span><span class="sxs-lookup"><span data-stu-id="9ad5d-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="9ad5d-106">入力</span><span class="sxs-lookup"><span data-stu-id="9ad5d-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="9ad5d-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ad5d-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ad5d-108">指定された係数を入力状態にエンコードするときに使用される近似許容範囲。</span><span class="sxs-lookup"><span data-stu-id="9ad5d-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="9ad5d-109">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9ad5d-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9ad5d-110">入力状態にエンコードされる係数。</span><span class="sxs-lookup"><span data-stu-id="9ad5d-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="9ad5d-111">出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="9ad5d-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="9ad5d-112">指定された係数を特定のレジスタの入力状態として準備する状態準備操作。</span><span class="sxs-lookup"><span data-stu-id="9ad5d-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>