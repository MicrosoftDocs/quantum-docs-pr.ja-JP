---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845776"
---
# <a name="indexrange-function"></a><span data-ttu-id="adb09-102">IndexRange 関数</span><span class="sxs-lookup"><span data-stu-id="adb09-102">IndexRange function</span></span>

<span data-ttu-id="adb09-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="adb09-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="adb09-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="adb09-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="adb09-105">配列を指定した場合は、その配列のインデックスに対する範囲を返します。 for ループでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="adb09-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="adb09-106">入力</span><span class="sxs-lookup"><span data-stu-id="adb09-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="adb09-107">配列: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="adb09-107">array : 'TElement[]</span></span>

<span data-ttu-id="adb09-108">インデックスの範囲を返す対象の配列。</span><span class="sxs-lookup"><span data-stu-id="adb09-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="adb09-109">出力: [範囲](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="adb09-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="adb09-110">配列のすべてのインデックスの範囲。</span><span class="sxs-lookup"><span data-stu-id="adb09-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="adb09-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="adb09-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="adb09-112">' TElement '</span><span class="sxs-lookup"><span data-stu-id="adb09-112">'TElement</span></span>

<span data-ttu-id="adb09-113">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="adb09-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="adb09-114">例</span><span class="sxs-lookup"><span data-stu-id="adb09-114">Example</span></span>

<span data-ttu-id="adb09-115">次の `for` ループは同等です。</span><span class="sxs-lookup"><span data-stu-id="adb09-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```