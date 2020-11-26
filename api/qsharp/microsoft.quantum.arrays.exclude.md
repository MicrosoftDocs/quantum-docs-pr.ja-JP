---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221353"
---
# <a name="exclude-function"></a><span data-ttu-id="6102c-102">Exclude 関数</span><span class="sxs-lookup"><span data-stu-id="6102c-102">Exclude function</span></span>

<span data-ttu-id="6102c-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6102c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6102c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6102c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6102c-105">指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="6102c-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="6102c-106">入力</span><span class="sxs-lookup"><span data-stu-id="6102c-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="6102c-107">削除: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6102c-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6102c-108">出力から除外する要素を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="6102c-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="6102c-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="6102c-109">array : 'T[]</span></span>

<span data-ttu-id="6102c-110">出力配列内の値を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="6102c-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="6102c-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="6102c-111">Output : 'T[]</span></span>

<span data-ttu-id="6102c-112">インデックスが `output` `output[0]` `array` に表示されない `remove` 、2番目の要素などのの最初の要素である配列 `output[1]` 。</span><span class="sxs-lookup"><span data-stu-id="6102c-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6102c-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6102c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6102c-114">&</span><span class="sxs-lookup"><span data-stu-id="6102c-114">'T</span></span>

<span data-ttu-id="6102c-115">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="6102c-115">The type of the array elements.</span></span>