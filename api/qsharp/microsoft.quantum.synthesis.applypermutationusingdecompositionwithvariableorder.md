---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203435"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="ec428-102">ApplyPermutationUsingDecompositionWithVariableOrder 操作</span><span class="sxs-lookup"><span data-stu-id="ec428-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="ec428-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ec428-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ec428-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec428-105">分解ベースの合成を使用する順列を指定して、クォンタムの状態の振幅を Permutes します。</span><span class="sxs-lookup"><span data-stu-id="ec428-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ec428-106">説明</span><span class="sxs-lookup"><span data-stu-id="ec428-106">Description</span></span>

<span data-ttu-id="ec428-107">この操作は、変数の順序を指定できるのより一般的なバージョンです @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 。</span><span class="sxs-lookup"><span data-stu-id="ec428-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="ec428-108">変数の順序が異なると、制御ゲートに使用される分解シーケンスと真理テーブルが変更され @"microsoft.quantum.intrinsic.x" ます。</span><span class="sxs-lookup"><span data-stu-id="ec428-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="ec428-109">したがって、変数の順序を変更すると、順列を実現するために使用されるゲート全体の数が変わります。</span><span class="sxs-lookup"><span data-stu-id="ec428-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="ec428-110">入力</span><span class="sxs-lookup"><span data-stu-id="ec428-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="ec428-111">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec428-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec428-112">0から始まる $ 2 ^ n $ 要素の順列。</span><span class="sxs-lookup"><span data-stu-id="ec428-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="ec428-113">変数の順序: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec428-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec428-114">0から始まる $ elements $n の順列。</span><span class="sxs-lookup"><span data-stu-id="ec428-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="ec428-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ec428-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ec428-116">順列が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="ec428-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec428-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec428-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ec428-118">参照</span><span class="sxs-lookup"><span data-stu-id="ec428-118">See Also</span></span>

- [<span data-ttu-id="ec428-119">ApplyPermutationUsingDecomposition です。</span><span class="sxs-lookup"><span data-stu-id="ec428-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="ec428-120">ApplyPermutationUsingTransformation です。</span><span class="sxs-lookup"><span data-stu-id="ec428-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)