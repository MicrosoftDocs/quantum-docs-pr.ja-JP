---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718915"
---
# <a name="rest-function"></a><span data-ttu-id="3daed-102">Rest 関数</span><span class="sxs-lookup"><span data-stu-id="3daed-102">Rest function</span></span>

<span data-ttu-id="3daed-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3daed-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3daed-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3daed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3daed-105">最初の配列要素が削除される点を除いて、入力配列と等しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="3daed-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3daed-106">入力</span><span class="sxs-lookup"><span data-stu-id="3daed-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3daed-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="3daed-107">array : 'T[]</span></span>

<span data-ttu-id="3daed-108">最後の要素が出力配列を形成する配列。</span><span class="sxs-lookup"><span data-stu-id="3daed-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="3daed-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="3daed-109">Output : 'T[]</span></span>

<span data-ttu-id="3daed-110">要素を格納している配列 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="3daed-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3daed-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3daed-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3daed-112">&</span><span class="sxs-lookup"><span data-stu-id="3daed-112">'T</span></span>

<span data-ttu-id="3daed-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="3daed-113">The type of the array elements.</span></span>