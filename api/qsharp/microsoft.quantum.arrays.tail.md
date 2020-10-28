---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718819"
---
# <a name="tail-function"></a><span data-ttu-id="d2da9-102">Tail 関数</span><span class="sxs-lookup"><span data-stu-id="d2da9-102">Tail function</span></span>

<span data-ttu-id="d2da9-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d2da9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d2da9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2da9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2da9-105">配列の最後の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="d2da9-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="d2da9-106">入力</span><span class="sxs-lookup"><span data-stu-id="d2da9-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="d2da9-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="d2da9-107">array : 'A[]</span></span>

<span data-ttu-id="d2da9-108">最後の要素が取得された配列。</span><span class="sxs-lookup"><span data-stu-id="d2da9-108">Array of which the last element is taken.</span></span> <span data-ttu-id="d2da9-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2da9-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="d2da9-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="d2da9-110">Output : 'A</span></span>

<span data-ttu-id="d2da9-111">配列の最後の要素。</span><span class="sxs-lookup"><span data-stu-id="d2da9-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d2da9-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2da9-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="d2da9-113">' A</span><span class="sxs-lookup"><span data-stu-id="d2da9-113">'A</span></span>

<span data-ttu-id="d2da9-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="d2da9-114">The type of the array elements.</span></span>