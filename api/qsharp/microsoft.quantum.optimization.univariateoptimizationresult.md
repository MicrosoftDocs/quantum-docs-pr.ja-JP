---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854566"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="4180d-102">UnivariateOptimizationResult ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="4180d-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="4180d-103">名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="4180d-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="4180d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4180d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4180d-105">Uni可変 ate 関数を最適化した結果を表します。</span><span class="sxs-lookup"><span data-stu-id="4180d-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="4180d-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="4180d-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="4180d-107">座標: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4180d-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4180d-108">最適なが見つかった入力。</span><span class="sxs-lookup"><span data-stu-id="4180d-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="4180d-109">値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4180d-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4180d-110">関数によって最適な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="4180d-110">Value returned by the function at its optimum.</span></span>