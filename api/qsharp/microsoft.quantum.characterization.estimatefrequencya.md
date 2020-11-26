---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204353"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="d1754-102">EstimateFrequencyA 操作</span><span class="sxs-lookup"><span data-stu-id="d1754-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="d1754-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d1754-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d1754-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1754-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1754-105">Adjointable と測定値の準備を行うと、は、 `Zero` 指定された数の試行を実行して、その測定が成功する頻度 (を返します) を推定します。</span><span class="sxs-lookup"><span data-stu-id="d1754-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d1754-106">入力</span><span class="sxs-lookup"><span data-stu-id="d1754-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="d1754-107">準備: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞</span><span class="sxs-lookup"><span data-stu-id="d1754-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d1754-108">入力レジスタに指定された状態 $ \rho $ を準備する adjointable 操作 ($ $P)。</span><span class="sxs-lookup"><span data-stu-id="d1754-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="d1754-109">測定値: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] =__無効 <Result>__></span><span class="sxs-lookup"><span data-stu-id="d1754-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="d1754-110">対象の測定値を表す $ $M 演算。</span><span class="sxs-lookup"><span data-stu-id="d1754-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d1754-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1754-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1754-112">準備と測定がそれぞれ作用する qubits の数。</span><span class="sxs-lookup"><span data-stu-id="d1754-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d1754-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1754-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1754-114">対象の頻度を推定するために測定を実行する回数。</span><span class="sxs-lookup"><span data-stu-id="d1754-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="d1754-115">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d1754-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d1754-116">\Hat{p} (P (\ket{00 \ ドット 0} \bra{00 \) $) $ が返さ $M れる頻度の推定 $ $ は、 `Zero` バイアスをかける二項分出し $ \hat{p} = n \_ {\uparrow}/n {\text{measurements}} $ を使用して取得し \_ ます。ここで、$n \_ {\uparrow} $ は観測された結果の数です `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="d1754-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1754-117">解説</span><span class="sxs-lookup"><span data-stu-id="d1754-117">Remarks</span></span>

<span data-ttu-id="d1754-118">Adjointable 操作の場合、操作の呼び出しなどの特定の仮定を行うと、qubits がまったく同じ状態になるように準備することができます。これにより、ターゲットマシンでパフォーマンスを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="d1754-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>