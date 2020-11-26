---
uid: Microsoft.Quantum.Arrays.Most
title: ほとんどの関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220605"
---
# <a name="most-function"></a><span data-ttu-id="109c5-102">ほとんどの関数</span><span class="sxs-lookup"><span data-stu-id="109c5-102">Most function</span></span>

<span data-ttu-id="109c5-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="109c5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="109c5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="109c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="109c5-105">最後の配列要素が削除される点を除いて、入力配列と等しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="109c5-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="109c5-106">入力</span><span class="sxs-lookup"><span data-stu-id="109c5-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="109c5-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="109c5-107">array : 'T[]</span></span>

<span data-ttu-id="109c5-108">最初から2番目の要素が出力配列を形成する配列。</span><span class="sxs-lookup"><span data-stu-id="109c5-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="109c5-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="109c5-109">Output : 'T[]</span></span>

<span data-ttu-id="109c5-110">要素を格納している配列 `array[0..Length(array) - 2]` 。</span><span class="sxs-lookup"><span data-stu-id="109c5-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="109c5-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="109c5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="109c5-112">&</span><span class="sxs-lookup"><span data-stu-id="109c5-112">'T</span></span>

<span data-ttu-id="109c5-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="109c5-113">The type of the array elements.</span></span>