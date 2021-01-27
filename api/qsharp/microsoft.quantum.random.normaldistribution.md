---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814183"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="041c5-102">NormalDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="041c5-102">NormalDistribution function</span></span>

<span data-ttu-id="041c5-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="041c5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="041c5-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="041c5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="041c5-105">指定された平均と分散を使用して正規分布を返します。</span><span class="sxs-lookup"><span data-stu-id="041c5-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="041c5-106">入力</span><span class="sxs-lookup"><span data-stu-id="041c5-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="041c5-107">平均: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="041c5-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="041c5-108">分散: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="041c5-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="041c5-109">出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="041c5-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="041c5-110">例</span><span class="sxs-lookup"><span data-stu-id="041c5-110">Example</span></span>

<span data-ttu-id="041c5-111">次の例では、平均2と標準偏差0.1 を使用して正規分布から10個のサンプルを描画します。</span><span class="sxs-lookup"><span data-stu-id="041c5-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="041c5-112">参照</span><span class="sxs-lookup"><span data-stu-id="041c5-112">See Also</span></span>

- [<span data-ttu-id="041c5-113">Microsoft............</span><span class="sxs-lookup"><span data-stu-id="041c5-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)