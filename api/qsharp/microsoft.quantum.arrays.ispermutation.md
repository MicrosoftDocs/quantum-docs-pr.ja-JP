---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848092"
---
# <a name="ispermutation-function"></a><span data-ttu-id="16cc5-102">IsPermutation 関数</span><span class="sxs-lookup"><span data-stu-id="16cc5-102">IsPermutation function</span></span>

<span data-ttu-id="16cc5-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="16cc5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="16cc5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16cc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16cc5-105">指定された配列が順列を表す場合にのみ、true を出力します。</span><span class="sxs-lookup"><span data-stu-id="16cc5-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="16cc5-106">説明</span><span class="sxs-lookup"><span data-stu-id="16cc5-106">Description</span></span>

<span data-ttu-id="16cc5-107">長さの配列を指定した場合は `array` `n` 、の各整数がに `0` `n - 1` 1 回だけ出現し `array` 、 `array` 要素の順列として解釈できる場合にのみ、true を返し `n` ます。</span><span class="sxs-lookup"><span data-stu-id="16cc5-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="16cc5-108">入力</span><span class="sxs-lookup"><span data-stu-id="16cc5-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="16cc5-109">permuation: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="16cc5-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="16cc5-110">順列を表すか、または表現できない配列。</span><span class="sxs-lookup"><span data-stu-id="16cc5-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="16cc5-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16cc5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="16cc5-112">例</span><span class="sxs-lookup"><span data-stu-id="16cc5-112">Example</span></span>

<span data-ttu-id="16cc5-113">次の Q # コードは、"すべての診断が正常に完了しました" というメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="16cc5-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="16cc5-114">解説</span><span class="sxs-lookup"><span data-stu-id="16cc5-114">Remarks</span></span>

<span data-ttu-id="16cc5-115">長さゼロの配列は、普通の順列です。</span><span class="sxs-lookup"><span data-stu-id="16cc5-115">An array of length zero is trivially a permutation.</span></span>