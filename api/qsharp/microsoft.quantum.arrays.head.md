---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719186"
---
# <a name="head-function"></a><span data-ttu-id="493c4-102">Head 関数</span><span class="sxs-lookup"><span data-stu-id="493c4-102">Head function</span></span>

<span data-ttu-id="493c4-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="493c4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="493c4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="493c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="493c4-105">配列の最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="493c4-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="493c4-106">入力</span><span class="sxs-lookup"><span data-stu-id="493c4-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="493c4-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="493c4-107">array : 'A[]</span></span>

<span data-ttu-id="493c4-108">最初の要素を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="493c4-108">Array of which the first element is taken.</span></span> <span data-ttu-id="493c4-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="493c4-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="493c4-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="493c4-110">Output : 'A</span></span>

<span data-ttu-id="493c4-111">配列の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="493c4-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="493c4-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="493c4-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="493c4-113">' A</span><span class="sxs-lookup"><span data-stu-id="493c4-113">'A</span></span>

<span data-ttu-id="493c4-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="493c4-114">The type of the array elements.</span></span>