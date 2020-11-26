---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211748"
---
# <a name="inputencoder-function"></a><span data-ttu-id="fa990-102">InputEncoder 関数</span><span class="sxs-lookup"><span data-stu-id="fa990-102">InputEncoder function</span></span>

<span data-ttu-id="fa990-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa990-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fa990-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa990-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fa990-105">係数と許容範囲を指定すると、は、各係数を計算ベース状態の対応する振幅として準備する状態準備操作を返します。</span><span class="sxs-lookup"><span data-stu-id="fa990-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="fa990-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa990-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="fa990-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fa990-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fa990-108">入力状態にエンコードされる係数。</span><span class="sxs-lookup"><span data-stu-id="fa990-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="fa990-109">出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="fa990-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="fa990-110">指定された係数を特定のレジスタの入力状態として準備する状態準備操作。</span><span class="sxs-lookup"><span data-stu-id="fa990-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>