---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204302"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="dbcad-102">EstimateOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="dbcad-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="dbcad-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="dbcad-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="dbcad-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbcad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbcad-105">それぞれの状態のコピーを準備する2つの操作を実行すると、各操作によって準備された状態間の2乗された重複が推定されます。</span><span class="sxs-lookup"><span data-stu-id="dbcad-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="dbcad-106">入力</span><span class="sxs-lookup"><span data-stu-id="dbcad-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="dbcad-107">preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="dbcad-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dbcad-108">比較する2つの状態準備操作の最初の。</span><span class="sxs-lookup"><span data-stu-id="dbcad-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="dbcad-109">preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="dbcad-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dbcad-110">比較する2つの状態準備操作の2番目の。</span><span class="sxs-lookup"><span data-stu-id="dbcad-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="dbcad-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbcad-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbcad-112">、、および all が動作する qubits の数 `commonPreparation` `preparation1` `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="dbcad-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="dbcad-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbcad-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbcad-114">重複の推定に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="dbcad-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="dbcad-115">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dbcad-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="dbcad-116">解説</span><span class="sxs-lookup"><span data-stu-id="dbcad-116">Remarks</span></span>

<span data-ttu-id="dbcad-117">この操作では、スワップテストを使用して $ $ \begin{align}/left | を検索します。\braket{00\cdots 0 |V ^ {\ dagger} U |00 \ cdots 0} \ 右 | ^ 2 \end{align} $ $ ここで $U $ は、のアクションのユニタリ表現で、 `preparation1` $V $ はに対応し `preparation2` ます。</span><span class="sxs-lookup"><span data-stu-id="dbcad-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbcad-118">参照</span><span class="sxs-lookup"><span data-stu-id="dbcad-118">See Also</span></span>

- [<span data-ttu-id="dbcad-119">EstimateRealOverlapBetweenStates (Microsoft... 特性)</span><span class="sxs-lookup"><span data-stu-id="dbcad-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="dbcad-120">EstimateImagOverlapBetweenStates (Microsoft... 特性)</span><span class="sxs-lookup"><span data-stu-id="dbcad-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)