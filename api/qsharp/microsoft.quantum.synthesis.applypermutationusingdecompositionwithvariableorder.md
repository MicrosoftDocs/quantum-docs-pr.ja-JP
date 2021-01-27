---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858877"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="afd76-102">ApplyPermutationUsingDecompositionWithVariableOrder 操作</span><span class="sxs-lookup"><span data-stu-id="afd76-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="afd76-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="afd76-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="afd76-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afd76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afd76-105">分解ベースの合成を使用する順列を指定して、クォンタムの状態の振幅を Permutes します。</span><span class="sxs-lookup"><span data-stu-id="afd76-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="afd76-106">説明</span><span class="sxs-lookup"><span data-stu-id="afd76-106">Description</span></span>

<span data-ttu-id="afd76-107">この操作は、変数の順序を指定できるのより一般的なバージョンです @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 。</span><span class="sxs-lookup"><span data-stu-id="afd76-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="afd76-108">変数の順序が異なると、制御ゲートに使用される分解シーケンスと真理テーブルが変更され @"microsoft.quantum.intrinsic.x" ます。</span><span class="sxs-lookup"><span data-stu-id="afd76-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="afd76-109">したがって、変数の順序を変更すると、順列を実現するために使用されるゲート全体の数が変わります。</span><span class="sxs-lookup"><span data-stu-id="afd76-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="afd76-110">入力</span><span class="sxs-lookup"><span data-stu-id="afd76-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="afd76-111">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="afd76-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="afd76-112">0から始まる $ 2 ^ n $ 要素の順列。</span><span class="sxs-lookup"><span data-stu-id="afd76-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="afd76-113">変数の順序: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="afd76-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="afd76-114">0から始まる $ elements $n の順列。</span><span class="sxs-lookup"><span data-stu-id="afd76-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="afd76-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="afd76-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="afd76-116">順列が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="afd76-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afd76-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afd76-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="afd76-118">例</span><span class="sxs-lookup"><span data-stu-id="afd76-118">Example</span></span>

<span data-ttu-id="afd76-119">操作を合成するには `SWAP` :</span><span class="sxs-lookup"><span data-stu-id="afd76-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="afd76-120">参照</span><span class="sxs-lookup"><span data-stu-id="afd76-120">See Also</span></span>

- [<span data-ttu-id="afd76-121">ApplyPermutationUsingDecomposition です。</span><span class="sxs-lookup"><span data-stu-id="afd76-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="afd76-122">ApplyPermutationUsingTransformation です。</span><span class="sxs-lookup"><span data-stu-id="afd76-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)