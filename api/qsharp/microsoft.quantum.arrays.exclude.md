---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719282"
---
# <a name="exclude-function"></a><span data-ttu-id="7aefd-102">Exclude 関数</span><span class="sxs-lookup"><span data-stu-id="7aefd-102">Exclude function</span></span>

<span data-ttu-id="7aefd-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7aefd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7aefd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7aefd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7aefd-105">指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7aefd-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7aefd-106">入力</span><span class="sxs-lookup"><span data-stu-id="7aefd-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="7aefd-107">削除: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7aefd-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7aefd-108">出力から除外する要素を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="7aefd-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="7aefd-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="7aefd-109">array : 'T[]</span></span>

<span data-ttu-id="7aefd-110">出力配列内の値を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="7aefd-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="7aefd-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="7aefd-111">Output : 'T[]</span></span>

<span data-ttu-id="7aefd-112">インデックスが `output` `output[0]` `array` に表示されない `remove` 、2番目の要素などのの最初の要素である配列 `output[1]` 。</span><span class="sxs-lookup"><span data-stu-id="7aefd-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7aefd-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7aefd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7aefd-114">&</span><span class="sxs-lookup"><span data-stu-id="7aefd-114">'T</span></span>

<span data-ttu-id="7aefd-115">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="7aefd-115">The type of the array elements.</span></span>