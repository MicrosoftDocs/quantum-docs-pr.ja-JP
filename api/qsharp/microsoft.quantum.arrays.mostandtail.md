---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Moスタンドテール関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845604"
---
# <a name="mostandtail-function"></a><span data-ttu-id="dd4de-102">Moスタンドテール関数</span><span class="sxs-lookup"><span data-stu-id="dd4de-102">MostAndTail function</span></span>

<span data-ttu-id="dd4de-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dd4de-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dd4de-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd4de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd4de-105">配列の最後の要素以外のすべてのタプルを返します。</span><span class="sxs-lookup"><span data-stu-id="dd4de-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="dd4de-106">入力</span><span class="sxs-lookup"><span data-stu-id="dd4de-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="dd4de-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="dd4de-107">array : 'A[]</span></span>

<span data-ttu-id="dd4de-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="dd4de-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="dd4de-109">出力: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="dd4de-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="dd4de-110">配列の1つ以上の最後の要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="dd4de-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dd4de-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd4de-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="dd4de-112">' A</span><span class="sxs-lookup"><span data-stu-id="dd4de-112">'A</span></span>

<span data-ttu-id="dd4de-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="dd4de-113">The type of the array elements.</span></span>