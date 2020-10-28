---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列挙関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719306"
---
# <a name="enumerated-function"></a><span data-ttu-id="34738-102">列挙関数</span><span class="sxs-lookup"><span data-stu-id="34738-102">Enumerated function</span></span>

<span data-ttu-id="34738-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="34738-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="34738-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34738-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34738-105">配列が指定された場合、は、元の配列の要素と各要素のインデックスを含む新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="34738-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="34738-106">入力</span><span class="sxs-lookup"><span data-stu-id="34738-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="34738-107">配列: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="34738-107">array : 'TElement[]</span></span>

<span data-ttu-id="34738-108">要素が列挙される配列。</span><span class="sxs-lookup"><span data-stu-id="34738-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="34738-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int), ' telement) []</span><span class="sxs-lookup"><span data-stu-id="34738-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="34738-110">元の配列の要素とそのインデックスを含む新しい配列。</span><span class="sxs-lookup"><span data-stu-id="34738-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34738-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="34738-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="34738-112">' TElement '</span><span class="sxs-lookup"><span data-stu-id="34738-112">'TElement</span></span>

<span data-ttu-id="34738-113">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="34738-113">The type of elements of the array.</span></span>