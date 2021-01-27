---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855525"
---
# <a name="decomposedon-function"></a><span data-ttu-id="32fb2-102">DecomposedOn 関数</span><span class="sxs-lookup"><span data-stu-id="32fb2-102">DecomposedOn function</span></span>

<span data-ttu-id="32fb2-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="32fb2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="32fb2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32fb2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32fb2-105">分解され変数の順列の並べ替え</span><span class="sxs-lookup"><span data-stu-id="32fb2-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="32fb2-106">説明</span><span class="sxs-lookup"><span data-stu-id="32fb2-106">Description</span></span>

<span data-ttu-id="32fb2-107">順列 $ \ pi $ ( `perm` ) とインデックス $i $ () に指定されてい `index` ます。このメソッドは3つの順列 $ ((\ pi_l, \ pi_r), \ pi ') $ を返します。 $ \ pi_l $ と $ \ pi_r $ のイメージでは、要素内の要素のビットを変更しないようにして、$-pi ' $ のイメージは、要素内でビット $i $ を変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="32fb2-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="32fb2-108">入力</span><span class="sxs-lookup"><span data-stu-id="32fb2-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="32fb2-109">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="32fb2-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="32fb2-110">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32fb2-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="32fb2-111">出力: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="32fb2-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="32fb2-112">例</span><span class="sxs-lookup"><span data-stu-id="32fb2-112">Example</span></span>

<span data-ttu-id="32fb2-113">入力が perm = [0, 2, 3, 5, 7, 1, 4, 6] および index = 0 であると仮定します。この関数は、次の表に基づいて3つの順列を計算します。これにより、グループ `perm` A の要素とグループ D のイメージ内の要素を含むバイナリ表記の順列が示されます。 列には、ビットインデックスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fb2-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="32fb2-114">|  |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="32fb2-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="32fb2-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-115">2 1 0</span></span> | <span data-ttu-id="32fb2-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-116">2 1 0</span></span> | <span data-ttu-id="32fb2-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-117">2 1 0</span></span> | <span data-ttu-id="32fb2-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="32fb2-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-119">0 0 0</span></span> |       |       | <span data-ttu-id="32fb2-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-120">0 0 0</span></span> | <span data-ttu-id="32fb2-121">0</span><span class="sxs-lookup"><span data-stu-id="32fb2-121">0</span></span>
| <span data-ttu-id="32fb2-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-122">0 0 1</span></span> |       |       | <span data-ttu-id="32fb2-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-123">0 1 0</span></span> | <span data-ttu-id="32fb2-124">2</span><span class="sxs-lookup"><span data-stu-id="32fb2-124">2</span></span>
| <span data-ttu-id="32fb2-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-125">0 1 0</span></span> |       |       | <span data-ttu-id="32fb2-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-126">0 1 1</span></span> | <span data-ttu-id="32fb2-127">3</span><span class="sxs-lookup"><span data-stu-id="32fb2-127">3</span></span>
| <span data-ttu-id="32fb2-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-128">0 1 1</span></span> |       |       | <span data-ttu-id="32fb2-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-129">1 0 1</span></span> | <span data-ttu-id="32fb2-130">5</span><span class="sxs-lookup"><span data-stu-id="32fb2-130">5</span></span>
| <span data-ttu-id="32fb2-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-131">1 0 0</span></span> |       |       | <span data-ttu-id="32fb2-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-132">1 1 1</span></span> | <span data-ttu-id="32fb2-133">7</span><span class="sxs-lookup"><span data-stu-id="32fb2-133">7</span></span>
| <span data-ttu-id="32fb2-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-134">1 0 1</span></span> |       |       | <span data-ttu-id="32fb2-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-135">0 0 1</span></span> | <span data-ttu-id="32fb2-136">1</span><span class="sxs-lookup"><span data-stu-id="32fb2-136">1</span></span>
| <span data-ttu-id="32fb2-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-137">1 1 0</span></span> |       |       | <span data-ttu-id="32fb2-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-138">1 0 0</span></span> | <span data-ttu-id="32fb2-139">4</span><span class="sxs-lookup"><span data-stu-id="32fb2-139">4</span></span>
| <span data-ttu-id="32fb2-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-140">1 1 1</span></span> |       |       | <span data-ttu-id="32fb2-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-141">1 1 0</span></span> | <span data-ttu-id="32fb2-142">6</span><span class="sxs-lookup"><span data-stu-id="32fb2-142">6</span></span>

<span data-ttu-id="32fb2-143">インデックスのすべての値が 0 (= インデックス) と等しくない場合は、A から B、D から C にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="32fb2-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="32fb2-144">|  |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="32fb2-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="32fb2-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-145">2 1 0</span></span> | <span data-ttu-id="32fb2-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-146">2 1 0</span></span> | <span data-ttu-id="32fb2-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-147">2 1 0</span></span> | <span data-ttu-id="32fb2-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="32fb2-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-149">0 0 0</span></span> | <span data-ttu-id="32fb2-150">0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-150">0 0</span></span>   | <span data-ttu-id="32fb2-151">0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-151">0 0</span></span>   | <span data-ttu-id="32fb2-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-152">0 0 0</span></span> |
| <span data-ttu-id="32fb2-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-153">0 0 1</span></span> | <span data-ttu-id="32fb2-154">0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-154">0 0</span></span>   | <span data-ttu-id="32fb2-155">0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-155">0 1</span></span>   | <span data-ttu-id="32fb2-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-156">0 1 0</span></span> |
| <span data-ttu-id="32fb2-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-157">0 1 0</span></span> | <span data-ttu-id="32fb2-158">0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-158">0 1</span></span>   | <span data-ttu-id="32fb2-159">0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-159">0 1</span></span>   | <span data-ttu-id="32fb2-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-160">0 1 1</span></span> |
| <span data-ttu-id="32fb2-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-161">0 1 1</span></span> | <span data-ttu-id="32fb2-162">0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-162">0 1</span></span>   | <span data-ttu-id="32fb2-163">1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-163">1 0</span></span>   | <span data-ttu-id="32fb2-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-164">1 0 1</span></span> |
| <span data-ttu-id="32fb2-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-165">1 0 0</span></span> | <span data-ttu-id="32fb2-166">1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-166">1 0</span></span>   | <span data-ttu-id="32fb2-167">1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-167">1 1</span></span>   | <span data-ttu-id="32fb2-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-168">1 1 1</span></span> |
| <span data-ttu-id="32fb2-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-169">1 0 1</span></span> | <span data-ttu-id="32fb2-170">1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-170">1 0</span></span>   | <span data-ttu-id="32fb2-171">0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-171">0 0</span></span>   | <span data-ttu-id="32fb2-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-172">0 0 1</span></span> |
| <span data-ttu-id="32fb2-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-173">1 1 0</span></span> | <span data-ttu-id="32fb2-174">1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-174">1 1</span></span>   | <span data-ttu-id="32fb2-175">1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-175">1 0</span></span>   | <span data-ttu-id="32fb2-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-176">1 0 0</span></span> |
| <span data-ttu-id="32fb2-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-177">1 1 1</span></span> | <span data-ttu-id="32fb2-178">1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-178">1 1</span></span>   | <span data-ttu-id="32fb2-179">1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-179">1 1</span></span>   | <span data-ttu-id="32fb2-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-180">1 1 0</span></span> |

<span data-ttu-id="32fb2-181">次に、ブロック B の列0に空のインデックスを持つ最初の要素に0が配置され、次に、プレフィックスが一致する B に1が配置されます (最初のケースでは、インデックスが 0 0 の他の行)。</span><span class="sxs-lookup"><span data-stu-id="32fb2-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="32fb2-182">その後、ブロック C の同じ行に1が追加され、ブロック C の対応するプレフィックスに対して0になります。 すべてのインデックスがブロック B および C の列0に配置されるまで、このプロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="32fb2-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="32fb2-183">|  |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="32fb2-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="32fb2-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-184">2 1 0</span></span> | <span data-ttu-id="32fb2-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-185">2 1 0</span></span> | <span data-ttu-id="32fb2-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-186">2 1 0</span></span> | <span data-ttu-id="32fb2-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="32fb2-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-188">0 0 0</span></span> | <span data-ttu-id="32fb2-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-189">0 0 0</span></span> | <span data-ttu-id="32fb2-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-190">0 0 0</span></span> | <span data-ttu-id="32fb2-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-191">0 0 0</span></span> |
| <span data-ttu-id="32fb2-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-192">0 0 1</span></span> | <span data-ttu-id="32fb2-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-193">0 0 1</span></span> | <span data-ttu-id="32fb2-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-194">0 1 1</span></span> | <span data-ttu-id="32fb2-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-195">0 1 0</span></span> |
| <span data-ttu-id="32fb2-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-196">0 1 0</span></span> | <span data-ttu-id="32fb2-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-197">0 1 0</span></span> | <span data-ttu-id="32fb2-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-198">0 1 0</span></span> | <span data-ttu-id="32fb2-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-199">0 1 1</span></span> |
| <span data-ttu-id="32fb2-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-200">0 1 1</span></span> | <span data-ttu-id="32fb2-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-201">0 1 1</span></span> | <span data-ttu-id="32fb2-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-202">1 0 1</span></span> | <span data-ttu-id="32fb2-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-203">1 0 1</span></span> |
| <span data-ttu-id="32fb2-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-204">1 0 0</span></span> | <span data-ttu-id="32fb2-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-205">1 0 0</span></span> | <span data-ttu-id="32fb2-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-206">1 1 0</span></span> | <span data-ttu-id="32fb2-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-207">1 1 1</span></span> |
| <span data-ttu-id="32fb2-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-208">1 0 1</span></span> | <span data-ttu-id="32fb2-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-209">1 0 1</span></span> | <span data-ttu-id="32fb2-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-210">0 0 1</span></span> | <span data-ttu-id="32fb2-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-211">0 0 1</span></span> |
| <span data-ttu-id="32fb2-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-212">1 1 0</span></span> | <span data-ttu-id="32fb2-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-213">1 1 0</span></span> | <span data-ttu-id="32fb2-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-214">1 0 0</span></span> | <span data-ttu-id="32fb2-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-215">1 0 0</span></span> |
| <span data-ttu-id="32fb2-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-216">1 1 1</span></span> | <span data-ttu-id="32fb2-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-217">1 1 1</span></span> | <span data-ttu-id="32fb2-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="32fb2-218">1 1 1</span></span> | <span data-ttu-id="32fb2-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="32fb2-219">1 1 0</span></span> |

<span data-ttu-id="32fb2-220">次の3つの新しい順列をテーブルから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="32fb2-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="32fb2-221">$ \ pi_l $、内の要素、B (左)</span><span class="sxs-lookup"><span data-stu-id="32fb2-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="32fb2-222">$ \ pi_r $、D の要素、C (right) のイメージ</span><span class="sxs-lookup"><span data-stu-id="32fb2-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="32fb2-223">$ \ pi ' $ B 内の要素、C のイメージ (残り)</span><span class="sxs-lookup"><span data-stu-id="32fb2-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="32fb2-224">ただし、$ \ pi_l $ と $ \ pi_r $ では、インデックス1と2には変更されません。また、$ \ pi_ ' $ in index 0 のビット値も変更されません。</span><span class="sxs-lookup"><span data-stu-id="32fb2-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="32fb2-225">また、$ \ pi_l $ と $ \ pi_r $ は自己逆にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="32fb2-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="32fb2-226">派生した順列は次のとおりです: left = [0, 1, 2, 3, 4, 5, 6, 7] right = [0, 1, 3, 2, 4, 5, 7, 6] 剰余 = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="32fb2-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>