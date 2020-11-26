---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191042"
---
# <a name="addfxp-operation"></a><span data-ttu-id="c59db-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="c59db-102">AddFxP operation</span></span>

<span data-ttu-id="c59db-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c59db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c59db-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c59db-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c59db-105">クォンタムレジスタに格納されている2つの固定小数点数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c59db-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c59db-106">説明</span><span class="sxs-lookup"><span data-stu-id="c59db-106">Description</span></span>

<span data-ttu-id="c59db-107">それぞれ、州 $ \ket{f_1} $ および $ \ket{f_2} $ に2つの固定小数点レジスタが指定されている場合、操作 $ \ket{f_1} \ket{f_2} \ map\ket{f_1} \ket{f_1 + f_2} $ が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c59db-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="c59db-108">入力</span><span class="sxs-lookup"><span data-stu-id="c59db-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="c59db-109">fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c59db-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c59db-110">最初の固定小数点数</span><span class="sxs-lookup"><span data-stu-id="c59db-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="c59db-111">fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c59db-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c59db-112">2番目の固定小数点数は、2つの入力の合計を含むように更新されます。</span><span class="sxs-lookup"><span data-stu-id="c59db-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c59db-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c59db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c59db-114">解説</span><span class="sxs-lookup"><span data-stu-id="c59db-114">Remarks</span></span>

<span data-ttu-id="c59db-115">現在の実装では、2つの固定小数点数が、最下位ビットから同じポイント位置を持つ必要があります。つまり、$n _i $ と $p _i は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c59db-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>