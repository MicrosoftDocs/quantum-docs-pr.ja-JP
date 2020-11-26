---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210031"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="da004-102">CumulativeFolded 関数</span><span class="sxs-lookup"><span data-stu-id="da004-102">CumulativeFolded function</span></span>

<span data-ttu-id="da004-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="da004-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="da004-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da004-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da004-105">マップされたフォールドを1つの関数に結合します</span><span class="sxs-lookup"><span data-stu-id="da004-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="da004-106">説明</span><span class="sxs-lookup"><span data-stu-id="da004-106">Description</span></span>

<span data-ttu-id="da004-107">この関数は、 `fn` 初期状態から開始 `state` し、初期状態を含まないすべての中間値を返す、配列を通じて関数を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="da004-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="da004-108">入力</span><span class="sxs-lookup"><span data-stu-id="da004-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="da004-109">fn: (' State, t)-> ' 状態</span><span class="sxs-lookup"><span data-stu-id="da004-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="da004-110">配列に対して折りたたむ関数</span><span class="sxs-lookup"><span data-stu-id="da004-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="da004-111">状態: ' 状態</span><span class="sxs-lookup"><span data-stu-id="da004-111">state : 'State</span></span>

<span data-ttu-id="da004-112">折りたたむ初期状態</span><span class="sxs-lookup"><span data-stu-id="da004-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="da004-113">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="da004-113">array : 'T[]</span></span>

<span data-ttu-id="da004-114">折りたたむ値の配列</span><span class="sxs-lookup"><span data-stu-id="da004-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="da004-115">出力: ' State []</span><span class="sxs-lookup"><span data-stu-id="da004-115">Output : 'State[]</span></span>

<span data-ttu-id="da004-116">最終状態を含むすべての中間状態。初期状態は含まれません。</span><span class="sxs-lookup"><span data-stu-id="da004-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="da004-117">出力配列の長さは、と同じ長さです `array` 。</span><span class="sxs-lookup"><span data-stu-id="da004-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="da004-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="da004-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="da004-119">' 状態</span><span class="sxs-lookup"><span data-stu-id="da004-119">'State</span></span>

<span data-ttu-id="da004-120">関数が操作する状態の種類 `fn` (つまり、最初の入力としてを受け取り、を返す)。</span><span class="sxs-lookup"><span data-stu-id="da004-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="da004-121">&</span><span class="sxs-lookup"><span data-stu-id="da004-121">'T</span></span>

<span data-ttu-id="da004-122">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="da004-122">The type of `array` elements.</span></span>