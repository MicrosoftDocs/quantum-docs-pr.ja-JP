---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714973"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="fd1c5-102">EstimateRealOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="fd1c5-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="fd1c5-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="fd1c5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd1c5-105">それぞれの状態のコピーを準備する2つの操作を実行すると、各操作によって準備された状態間の重複部分が推定されます。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="fd1c5-106">入力</span><span class="sxs-lookup"><span data-stu-id="fd1c5-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="fd1c5-107">commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="fd1c5-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fd1c5-108">固定の入力状態を準備する操作。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="fd1c5-109">preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fd1c5-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="fd1c5-110">比較する2つの状態準備操作の最初の。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="fd1c5-111">preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fd1c5-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="fd1c5-112">比較する2つの状態準備操作の2番目の。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="fd1c5-113">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd1c5-114">、、および all が動作する qubits の数 `commonPreparation` `preparation1` `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="fd1c5-115">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd1c5-116">重複の推定に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="fd1c5-117">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="fd1c5-118">解説</span><span class="sxs-lookup"><span data-stu-id="fd1c5-118">Remarks</span></span>

<span data-ttu-id="fd1c5-119">この操作では、Hadamard テストを使用して、$ $ \begin{align} \braket{\psi | の実数部を検索します。V ^ {\ dagger} U |\psi} \end{align} $ $ ここで、$ \ket{\psi} $ はによって準備された状態であり `commonPreparation` $U、$ はのアクションのユニタリ表現で `preparation1` あり、$V $ はに対応し `preparation2` ます。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="fd1c5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd1c5-120">References</span></span>

- <span data-ttu-id="fd1c5-121">Aharonov *et al.* [/0511096 のように](https://arxiv.org/abs/quant-ph/0511096)なります。</span><span class="sxs-lookup"><span data-stu-id="fd1c5-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd1c5-122">参照</span><span class="sxs-lookup"><span data-stu-id="fd1c5-122">See Also</span></span>

- [<span data-ttu-id="fd1c5-123">EstimateImagOverlapBetweenStates (Microsoft... 特性)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="fd1c5-124">EstimateOverlapBetweenStates (Microsoft... 特性)</span><span class="sxs-lookup"><span data-stu-id="fd1c5-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)