---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854606"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="bb944-102">LocalUnivariateMinimum 関数</span><span class="sxs-lookup"><span data-stu-id="bb944-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="bb944-103">名前空間: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="bb944-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="bb944-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb944-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb944-105">ゴールデン interval 検索を使用して、範囲指定された期間にわたって、uni可変 ate 関数のローカル最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="bb944-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="bb944-106">入力</span><span class="sxs-lookup"><span data-stu-id="bb944-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="bb944-107">fn: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb944-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb944-108">最小化される uniバリエーション関数。</span><span class="sxs-lookup"><span data-stu-id="bb944-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="bb944-109">境界: ([double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="bb944-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="bb944-110">ローカル最小値が検索される間隔。</span><span class="sxs-lookup"><span data-stu-id="bb944-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="bb944-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb944-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb944-112">許容される関数入力の精度。</span><span class="sxs-lookup"><span data-stu-id="bb944-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="bb944-113">ローカル最適化 a の検索は、間隔がこの許容範囲を下回るまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="bb944-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="bb944-114">出力: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="bb944-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="bb944-115">指定された範囲内にある、指定された関数のローカル最適化 a。</span><span class="sxs-lookup"><span data-stu-id="bb944-115">A local optima of the given function, located within the given bounds.</span></span>