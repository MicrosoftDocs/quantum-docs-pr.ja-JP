---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719107"
---
# <a name="ispermutation-function"></a><span data-ttu-id="c30dc-102">IsPermutation 関数</span><span class="sxs-lookup"><span data-stu-id="c30dc-102">IsPermutation function</span></span>

<span data-ttu-id="c30dc-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c30dc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c30dc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c30dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c30dc-105">指定された配列が順列を表す場合にのみ、true を出力します。</span><span class="sxs-lookup"><span data-stu-id="c30dc-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c30dc-106">説明</span><span class="sxs-lookup"><span data-stu-id="c30dc-106">Description</span></span>

<span data-ttu-id="c30dc-107">長さの配列を指定した場合は `array` `n` 、の各整数がに `0` `n - 1` 1 回だけ出現し `array` 、 `array` 要素の順列として解釈できる場合にのみ、true を返し `n` ます。</span><span class="sxs-lookup"><span data-stu-id="c30dc-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="c30dc-108">入力</span><span class="sxs-lookup"><span data-stu-id="c30dc-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="c30dc-109">permuation: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c30dc-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c30dc-110">順列を表すか、または表現できない配列。</span><span class="sxs-lookup"><span data-stu-id="c30dc-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c30dc-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c30dc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="c30dc-112">解説</span><span class="sxs-lookup"><span data-stu-id="c30dc-112">Remarks</span></span>

<span data-ttu-id="c30dc-113">長さゼロの配列は、普通の順列です。</span><span class="sxs-lookup"><span data-stu-id="c30dc-113">An array of length zero is trivially a permutation.</span></span>