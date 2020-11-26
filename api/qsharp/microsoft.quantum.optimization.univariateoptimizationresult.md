---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194034"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="fb7ae-102">UnivariateOptimizationResult ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="fb7ae-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="fb7ae-103">名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="fb7ae-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="fb7ae-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb7ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb7ae-105">Uni可変 ate 関数を最適化した結果を表します。</span><span class="sxs-lookup"><span data-stu-id="fb7ae-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="fb7ae-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="fb7ae-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="fb7ae-107">座標: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb7ae-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb7ae-108">最適なが見つかった入力。</span><span class="sxs-lookup"><span data-stu-id="fb7ae-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="fb7ae-109">値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb7ae-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb7ae-110">関数によって最適な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="fb7ae-110">Value returned by the function at its optimum.</span></span>