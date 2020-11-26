---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 23f336da77135820c46d1d76a196c6d453f1322f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221506"
---
# <a name="elementat-function"></a><span data-ttu-id="a0cc5-102">ElementAt 関数</span><span class="sxs-lookup"><span data-stu-id="a0cc5-102">ElementAt function</span></span>

<span data-ttu-id="a0cc5-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0cc5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0cc5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0cc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0cc5-105">配列の指定したインデックス位置にあるを返します。</span><span class="sxs-lookup"><span data-stu-id="a0cc5-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="a0cc5-106">入力</span><span class="sxs-lookup"><span data-stu-id="a0cc5-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="a0cc5-107">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a0cc5-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a0cc5-108">要素のインデックス</span><span class="sxs-lookup"><span data-stu-id="a0cc5-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="a0cc5-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="a0cc5-109">array : 'T[]</span></span>

<span data-ttu-id="a0cc5-110">インデックスが作成される配列。</span><span class="sxs-lookup"><span data-stu-id="a0cc5-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="a0cc5-111">出力: t</span><span class="sxs-lookup"><span data-stu-id="a0cc5-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a0cc5-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0cc5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0cc5-113">&</span><span class="sxs-lookup"><span data-stu-id="a0cc5-113">'T</span></span>

<span data-ttu-id="a0cc5-114">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a0cc5-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0cc5-115">参照</span><span class="sxs-lookup"><span data-stu-id="a0cc5-115">See Also</span></span>

- [<span data-ttu-id="a0cc5-116">Microsoft. Quantum. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="a0cc5-116">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="a0cc5-117">Microsoft... Arrays. ElementsAt</span><span class="sxs-lookup"><span data-stu-id="a0cc5-117">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)