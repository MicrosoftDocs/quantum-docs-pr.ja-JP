---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列挙関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848123"
---
# <a name="enumerated-function"></a><span data-ttu-id="92c5b-102">列挙関数</span><span class="sxs-lookup"><span data-stu-id="92c5b-102">Enumerated function</span></span>

<span data-ttu-id="92c5b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="92c5b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="92c5b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92c5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92c5b-105">配列が指定された場合、は、元の配列の要素と各要素のインデックスを含む新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="92c5b-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="92c5b-106">入力</span><span class="sxs-lookup"><span data-stu-id="92c5b-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="92c5b-107">配列: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="92c5b-107">array : 'TElement[]</span></span>

<span data-ttu-id="92c5b-108">要素が列挙される配列。</span><span class="sxs-lookup"><span data-stu-id="92c5b-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="92c5b-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int), ' telement) []</span><span class="sxs-lookup"><span data-stu-id="92c5b-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="92c5b-110">元の配列の要素とそのインデックスを含む新しい配列。</span><span class="sxs-lookup"><span data-stu-id="92c5b-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="92c5b-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="92c5b-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="92c5b-112">' TElement '</span><span class="sxs-lookup"><span data-stu-id="92c5b-112">'TElement</span></span>

<span data-ttu-id="92c5b-113">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="92c5b-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="92c5b-114">例</span><span class="sxs-lookup"><span data-stu-id="92c5b-114">Example</span></span>

<span data-ttu-id="92c5b-115">次の `for` ループは同等です。</span><span class="sxs-lookup"><span data-stu-id="92c5b-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```