---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Moスタンドテール関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220571"
---
# <a name="mostandtail-function"></a><span data-ttu-id="ea038-102">Moスタンドテール関数</span><span class="sxs-lookup"><span data-stu-id="ea038-102">MostAndTail function</span></span>

<span data-ttu-id="ea038-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ea038-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ea038-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea038-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea038-105">配列の最後の要素以外のすべてのタプルを返します。</span><span class="sxs-lookup"><span data-stu-id="ea038-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="ea038-106">入力</span><span class="sxs-lookup"><span data-stu-id="ea038-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="ea038-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="ea038-107">array : 'A[]</span></span>

<span data-ttu-id="ea038-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="ea038-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="ea038-109">出力: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="ea038-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="ea038-110">配列の1つ以上の最後の要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="ea038-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ea038-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea038-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="ea038-112">' A</span><span class="sxs-lookup"><span data-stu-id="ea038-112">'A</span></span>

<span data-ttu-id="ea038-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ea038-113">The type of the array elements.</span></span>