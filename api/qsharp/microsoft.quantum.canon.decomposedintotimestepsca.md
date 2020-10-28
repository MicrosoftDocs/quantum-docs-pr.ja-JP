---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716340"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="29fbb-102">DecomposedIntoTimeStepsCA 関数</span><span class="sxs-lookup"><span data-stu-id="29fbb-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="29fbb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29fbb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29fbb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29fbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29fbb-105">指定された操作に対して Trotter – Suzuki インテグレーターを実装する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="29fbb-106">入力</span><span class="sxs-lookup"><span data-stu-id="29fbb-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="29fbb-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29fbb-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29fbb-108">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="29fbb-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="29fbb-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="29fbb-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="29fbb-110">分解のためのインデックス入力 (型 `Int` ) と時間入力 (型) を受け入れる操作 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="29fbb-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="29fbb-111">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29fbb-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29fbb-112">使用する Trotter – Suzuki インテグレーターの順序を選択します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="29fbb-113">注文1と注文2、4、6,...は現在サポートされています。</span><span class="sxs-lookup"><span data-stu-id="29fbb-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="29fbb-114">出力: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="29fbb-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="29fbb-115">Trotter – Suzuki インテグレーターを実装するユニタリを返します。最初のパラメーターは `Double` 統合ステップサイズで、2番目のパラメーターは操作対象のターゲットです。</span><span class="sxs-lookup"><span data-stu-id="29fbb-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29fbb-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="29fbb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29fbb-117">&</span><span class="sxs-lookup"><span data-stu-id="29fbb-117">'T</span></span>

<span data-ttu-id="29fbb-118">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="29fbb-119">解説</span><span class="sxs-lookup"><span data-stu-id="29fbb-119">Remarks</span></span>

<span data-ttu-id="29fbb-120">と等しいを指定して呼び出された場合 `order` `1` 、この関数は、最も低い順序の Trotter – Suzuki インテグレーター $ $ \begin{align} S_1 (\ ラムダ) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, によってシミュレートできる操作を返します。 \end{align} $ $ は、 [quant-ph/0508139 の](https://arxiv.org/abs/quant-ph/0508139) 表記に従い、$/ラムダ $ を進化時間 (返された操作の最初の入力で表される) にします。また、$ H_j \{ _ \} {j = 1} ^ {m} $ は、Dynamical ジェネレーターのセット (Hermitian) として統合されています。これにより、ジェネレーターは、' ^ `op(j, lambda, _)` {H_j \lambda} $ という単位で、ジェネレーターがシミュレートされます。 $e</span><span class="sxs-lookup"><span data-stu-id="29fbb-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="29fbb-121">同様に、 `order` のは、 `2` 2 番目の順序の対称 Trotter – Suzuki インテグレーター $ $ \begin{align} S_2 (\ ラムダ) = \ prod_ {j = 1} ^ {m} e ^ {H_k/ラムダ/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \ ラムダ/2} を返します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="29fbb-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="29fbb-122">\end{align} $$</span></span>

<span data-ttu-id="29fbb-123">の値が大きいほど、 `order` [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)の再帰的な構築を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="29fbb-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="29fbb-124">References</span></span>

- [<span data-ttu-id="29fbb-125">*Berry、G. Ahokas、Cleve、サンダース、のよう* になります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)