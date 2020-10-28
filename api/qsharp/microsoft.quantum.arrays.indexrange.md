---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719150"
---
# <a name="indexrange-function"></a><span data-ttu-id="21d5f-102">IndexRange 関数</span><span class="sxs-lookup"><span data-stu-id="21d5f-102">IndexRange function</span></span>

<span data-ttu-id="21d5f-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21d5f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21d5f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21d5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21d5f-105">配列を指定した場合は、その配列のインデックスに対する範囲を返します。 for ループでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="21d5f-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="21d5f-106">入力</span><span class="sxs-lookup"><span data-stu-id="21d5f-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="21d5f-107">配列: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="21d5f-107">array : 'TElement[]</span></span>

<span data-ttu-id="21d5f-108">インデックスの範囲を返す対象の配列。</span><span class="sxs-lookup"><span data-stu-id="21d5f-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="21d5f-109">出力: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="21d5f-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="21d5f-110">配列のすべてのインデックスの範囲。</span><span class="sxs-lookup"><span data-stu-id="21d5f-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="21d5f-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="21d5f-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="21d5f-112">' TElement '</span><span class="sxs-lookup"><span data-stu-id="21d5f-112">'TElement</span></span>

<span data-ttu-id="21d5f-113">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="21d5f-113">The type of elements of the array.</span></span>