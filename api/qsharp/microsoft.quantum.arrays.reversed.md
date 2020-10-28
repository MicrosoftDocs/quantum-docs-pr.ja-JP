---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反転関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718910"
---
# <a name="reversed-function"></a><span data-ttu-id="ba7e0-102">反転関数</span><span class="sxs-lookup"><span data-stu-id="ba7e0-102">Reversed function</span></span>

<span data-ttu-id="ba7e0-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ba7e0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ba7e0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba7e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba7e0-105">入力配列と同じ要素が逆順に含まれる配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="ba7e0-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ba7e0-106">入力</span><span class="sxs-lookup"><span data-stu-id="ba7e0-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ba7e0-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="ba7e0-107">array : 'T[]</span></span>

<span data-ttu-id="ba7e0-108">逆の順序で要素をコピーする配列。</span><span class="sxs-lookup"><span data-stu-id="ba7e0-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="ba7e0-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="ba7e0-109">Output : 'T[]</span></span>

<span data-ttu-id="ba7e0-110">要素を格納している配列 `array[Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="ba7e0-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="ba7e0-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="ba7e0-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba7e0-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba7e0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba7e0-113">&</span><span class="sxs-lookup"><span data-stu-id="ba7e0-113">'T</span></span>

<span data-ttu-id="ba7e0-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ba7e0-114">The type of the array elements.</span></span>