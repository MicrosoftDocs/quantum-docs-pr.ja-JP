---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857389"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="3f4df-102">ApplyPermutationUsingDecomposition 操作</span><span class="sxs-lookup"><span data-stu-id="3f4df-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="3f4df-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3f4df-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3f4df-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f4df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f4df-105">分解ベースの合成を使用する順列を指定して、クォンタムの状態の振幅を Permutes します。</span><span class="sxs-lookup"><span data-stu-id="3f4df-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3f4df-106">説明</span><span class="sxs-lookup"><span data-stu-id="3f4df-106">Description</span></span>

<span data-ttu-id="3f4df-107">この手順では、分解ベースの合成アプローチを実装します。</span><span class="sxs-lookup"><span data-stu-id="3f4df-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="3f4df-108">入力は、$ 2 ^ n $ 要素の順列 $ \ pi $ ($ \{ 0, \ ドット, 2 ^ n-1 $) で、 \} $n $ 変数の元に戻せるブール関数を表します。</span><span class="sxs-lookup"><span data-stu-id="3f4df-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="3f4df-109">このアルゴリズムでは、変数インデックス $i $: の各変数について、次の手順を繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="3f4df-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="3f4df-110">Compute $ ((\ pi_l, \ pi_r), \ pi ') $ では、$ \ pi_l $ と $ \ pi_r $ のイメージは、要素内のビットを変更しないようにします。 $ \ $ および $ \ $ は、$-pi ' $ のイメージではなく、要素内のビット $i $ を変更しません。</span><span class="sxs-lookup"><span data-stu-id="3f4df-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="3f4df-111">$ \ Pi \leftarrow \ pi ' $ を設定し、固定ポイントではない要素に基づいて $ \ pi_l $ と $ \ pi_r $ から真理のテーブルを派生させます。</span><span class="sxs-lookup"><span data-stu-id="3f4df-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="3f4df-112">すべての変数インデックスに対してこれらの手順を適用すると、残りの順列 $ \ pi $ が id になります。また、収集された真理テーブルとインデックスに基づいて、 @"microsoft.quantum.intrinsic.x" 操作を使用して、実際のテーブルで制御される操作を適用でき @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ます。</span><span class="sxs-lookup"><span data-stu-id="3f4df-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="3f4df-113">変数の順序は、$0、\ ドット、n-$1 です。</span><span class="sxs-lookup"><span data-stu-id="3f4df-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="3f4df-114">操作には、カスタム変数の順序を指定でき @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" ます。</span><span class="sxs-lookup"><span data-stu-id="3f4df-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="3f4df-115">入力</span><span class="sxs-lookup"><span data-stu-id="3f4df-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="3f4df-116">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3f4df-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3f4df-117">0から始まる $ 2 ^ n $ 要素の順列。</span><span class="sxs-lookup"><span data-stu-id="3f4df-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3f4df-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f4df-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f4df-119">順列が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="3f4df-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f4df-120">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f4df-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="3f4df-121">例</span><span class="sxs-lookup"><span data-stu-id="3f4df-121">Example</span></span>

<span data-ttu-id="3f4df-122">操作を合成するには `SWAP` :</span><span class="sxs-lookup"><span data-stu-id="3f4df-122">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="3f4df-123">References</span><span class="sxs-lookup"><span data-stu-id="3f4df-123">References</span></span>

- [<span data-ttu-id="3f4df-124">*Alexis De Vos*、 *Yvan Van rentergem*、Adv ((2)、2008、pp. 183--200)</span><span class="sxs-lookup"><span data-stu-id="3f4df-124">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="3f4df-125">*Mathias Soeken*、 *山久 tague*、 *gerhard W Dueck*、 *rolf Drechsler*、シンボル計算のジャーナル 73 (2016)、pp. 1--26</span><span class="sxs-lookup"><span data-stu-id="3f4df-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="3f4df-126">参照</span><span class="sxs-lookup"><span data-stu-id="3f4df-126">See Also</span></span>

- [<span data-ttu-id="3f4df-127">ApplyPermutationUsingDecompositionWithVariableOrder です。</span><span class="sxs-lookup"><span data-stu-id="3f4df-127">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="3f4df-128">ApplyPermutationUsingTransformation です。</span><span class="sxs-lookup"><span data-stu-id="3f4df-128">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)