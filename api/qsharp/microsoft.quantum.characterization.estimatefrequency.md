---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715085"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="96042-102">EstimateFrequency 操作</span><span class="sxs-lookup"><span data-stu-id="96042-102">EstimateFrequency operation</span></span>

<span data-ttu-id="96042-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="96042-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="96042-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96042-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96042-105">準備と測定値を指定すると、指定された数の試行回数を実行することで、測定が成功する頻度 (を返します) を推定し `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="96042-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="96042-106">入力</span><span class="sxs-lookup"><span data-stu-id="96042-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="96042-107">準備: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96042-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="96042-108">入力レジスタに特定の状態 $ \rho $ を準備する、$ $P の操作。</span><span class="sxs-lookup"><span data-stu-id="96042-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="96042-109">測定値: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = __無効 <Result>__ ></span><span class="sxs-lookup"><span data-stu-id="96042-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="96042-110">対象の測定値を表す $ $M 演算。</span><span class="sxs-lookup"><span data-stu-id="96042-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="96042-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96042-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96042-112">準備と測定がそれぞれ作用する qubits の数。</span><span class="sxs-lookup"><span data-stu-id="96042-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="96042-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96042-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96042-114">対象の頻度を推定するために測定を実行する回数。</span><span class="sxs-lookup"><span data-stu-id="96042-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="96042-115">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96042-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96042-116">\Hat{p} (P (\ket{00 \ ドット 0} \bra{00 \) $) $ が返さ $M れる頻度の推定 $ $ は、 `Zero` バイアスをかける二項分出し $ \hat{p} = n \_ {\uparrow}/n {\text{measurements}} $ を使用して取得し \_ ます。ここで、$n \_ {\uparrow} $ は観測された結果の数です `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="96042-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="96042-117">これは、物理的な制限を尊重するターゲットコンピューターでは特に重要であり、確率を測定できないようにします。</span><span class="sxs-lookup"><span data-stu-id="96042-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>