---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721699"
---
# <a name="addfxp-operation"></a><span data-ttu-id="84f59-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="84f59-102">AddFxP operation</span></span>

<span data-ttu-id="84f59-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84f59-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84f59-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84f59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84f59-105">クォンタムレジスタに格納されている2つの固定小数点数を追加します。</span><span class="sxs-lookup"><span data-stu-id="84f59-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="84f59-106">説明</span><span class="sxs-lookup"><span data-stu-id="84f59-106">Description</span></span>

<span data-ttu-id="84f59-107">それぞれ、州 $ \ket{f_1} $ および $ \ket{f_2} $ に2つの固定小数点レジスタが指定されている場合、操作 $ \ket{f_1} \ket{f_2} \ map\ket{f_1} \ket{f_1 + f_2} $ が実行されます。</span><span class="sxs-lookup"><span data-stu-id="84f59-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="84f59-108">入力</span><span class="sxs-lookup"><span data-stu-id="84f59-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="84f59-109">fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="84f59-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="84f59-110">最初の固定小数点数</span><span class="sxs-lookup"><span data-stu-id="84f59-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="84f59-111">fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="84f59-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="84f59-112">2番目の固定小数点数は、2つの入力の合計を含むように更新されます。</span><span class="sxs-lookup"><span data-stu-id="84f59-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84f59-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84f59-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="84f59-114">解説</span><span class="sxs-lookup"><span data-stu-id="84f59-114">Remarks</span></span>

<span data-ttu-id="84f59-115">現在の実装では、2つの固定小数点数が、最下位ビットから同じポイント位置を持つ必要があります。つまり、$n _i $ と $p _i は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f59-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>