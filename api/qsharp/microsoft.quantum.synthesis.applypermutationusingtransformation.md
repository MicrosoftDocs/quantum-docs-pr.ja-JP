---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725290"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="21c8b-102">ApplyPermutationUsingTransformation 操作</span><span class="sxs-lookup"><span data-stu-id="21c8b-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="21c8b-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="21c8b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="21c8b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21c8b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21c8b-105">変換ベースの合成を使用した順列を指定して、クォンタムの状態の振幅を Permutes します。</span><span class="sxs-lookup"><span data-stu-id="21c8b-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="21c8b-106">説明</span><span class="sxs-lookup"><span data-stu-id="21c8b-106">Description</span></span>

<span data-ttu-id="21c8b-107">この手順では、一方向の変換に基づく合成アプローチを実装します。</span><span class="sxs-lookup"><span data-stu-id="21c8b-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="21c8b-108">入力は、$ 2 ^ n $ 要素の順列 $ \ pi $ ($ \{ 0, \ ドット, 2 ^ n-1 $) で、 \} $n $ 変数の元に戻せるブール関数を表します。</span><span class="sxs-lookup"><span data-stu-id="21c8b-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="21c8b-109">アルゴリズムは、次の手順を繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="21c8b-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="21c8b-110">$X \n e & pi (x) = y $ のように、最小の $x $ を検索します。</span><span class="sxs-lookup"><span data-stu-id="21c8b-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="21c8b-111">出力に適用される複数の制御された Toffoli 操作を見つけます $ \ pi (x) = x $、すべての $x ' < x $ の $ \ pi (x ') $ を変更しません</span><span class="sxs-lookup"><span data-stu-id="21c8b-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="21c8b-112">入力</span><span class="sxs-lookup"><span data-stu-id="21c8b-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="21c8b-113">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="21c8b-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="21c8b-114">0から始まる $ 2 ^ n $ 要素の順列。</span><span class="sxs-lookup"><span data-stu-id="21c8b-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="21c8b-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21c8b-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21c8b-116">順列が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="21c8b-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21c8b-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21c8b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="21c8b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="21c8b-118">References</span></span>

- [<span data-ttu-id="21c8b-119">*D. Michael 明美* 、 *Dmitri Maslov* 、 *gerhard W. Dueck* 、Proc. DAC 2003、IEEE、pp. 318-323、2003</span><span class="sxs-lookup"><span data-stu-id="21c8b-119">*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck* , Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="21c8b-120">*Mathias Soeken* 、 *Gerhard W. Dueck* 2016 *、springer link* 、、pp. 307-321、2016を行います。</span><span class="sxs-lookup"><span data-stu-id="21c8b-120">*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="21c8b-121">参照</span><span class="sxs-lookup"><span data-stu-id="21c8b-121">See Also</span></span>

- [<span data-ttu-id="21c8b-122">ApplyPermutationUsingDecomposition です。</span><span class="sxs-lookup"><span data-stu-id="21c8b-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)