---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724324"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="c0e1c-102">UnivariateOptimizationResult ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="c0e1c-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="c0e1c-103">名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="c0e1c-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="c0e1c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0e1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0e1c-105">Uni可変 ate 関数を最適化した結果を表します。</span><span class="sxs-lookup"><span data-stu-id="c0e1c-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="c0e1c-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="c0e1c-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="c0e1c-107">座標: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0e1c-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0e1c-108">最適なが見つかった入力。</span><span class="sxs-lookup"><span data-stu-id="c0e1c-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="c0e1c-109">値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0e1c-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0e1c-110">関数によって最適な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="c0e1c-110">Value returned by the function at its optimum.</span></span>