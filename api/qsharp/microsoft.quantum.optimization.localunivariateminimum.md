---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: e804e6a6ed82f14dcc9b8f721ad503d77922dc0f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194085"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="4deb8-102">LocalUnivariateMinimum 関数</span><span class="sxs-lookup"><span data-stu-id="4deb8-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="4deb8-103">名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="4deb8-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="4deb8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4deb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4deb8-105">ゴールデン interval 検索を使用して、範囲指定された期間にわたって、uni可変 ate 関数のローカル最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="4deb8-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="4deb8-106">入力</span><span class="sxs-lookup"><span data-stu-id="4deb8-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="4deb8-107">fn: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4deb8-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4deb8-108">最小化される uniバリエーション関数。</span><span class="sxs-lookup"><span data-stu-id="4deb8-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="4deb8-109">境界: ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="4deb8-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="4deb8-110">ローカル最小値が検索される間隔。</span><span class="sxs-lookup"><span data-stu-id="4deb8-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4deb8-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4deb8-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4deb8-112">許容される関数入力の精度。</span><span class="sxs-lookup"><span data-stu-id="4deb8-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="4deb8-113">ローカル最適化 a の検索は、間隔がこの許容範囲を下回るまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="4deb8-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="4deb8-114">出力: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="4deb8-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="4deb8-115">指定された範囲内にある、指定された関数のローカル最適化 a。</span><span class="sxs-lookup"><span data-stu-id="4deb8-115">A local optima of the given function, located within the given bounds.</span></span>