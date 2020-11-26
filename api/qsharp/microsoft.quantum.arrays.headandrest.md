---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: ヘッド Andrest 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221081"
---
# <a name="headandrest-function"></a><span data-ttu-id="23d4b-102">ヘッド Andrest 関数</span><span class="sxs-lookup"><span data-stu-id="23d4b-102">HeadAndRest function</span></span>

<span data-ttu-id="23d4b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23d4b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23d4b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23d4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23d4b-105">配列の最初の要素と残りのすべての要素の組を返します。</span><span class="sxs-lookup"><span data-stu-id="23d4b-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="23d4b-106">入力</span><span class="sxs-lookup"><span data-stu-id="23d4b-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="23d4b-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="23d4b-107">array : 'A[]</span></span>

<span data-ttu-id="23d4b-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="23d4b-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="23d4b-109">出力: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="23d4b-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="23d4b-110">配列の最初の要素と残りのすべての要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="23d4b-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23d4b-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="23d4b-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="23d4b-112">' A</span><span class="sxs-lookup"><span data-stu-id="23d4b-112">'A</span></span>

<span data-ttu-id="23d4b-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="23d4b-113">The type of the array elements.</span></span>