---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: ヘッド Andrest 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848558"
---
# <a name="headandrest-function"></a><span data-ttu-id="83a08-102">ヘッド Andrest 関数</span><span class="sxs-lookup"><span data-stu-id="83a08-102">HeadAndRest function</span></span>

<span data-ttu-id="83a08-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="83a08-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="83a08-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83a08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83a08-105">配列の最初の要素と残りのすべての要素の組を返します。</span><span class="sxs-lookup"><span data-stu-id="83a08-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="83a08-106">入力</span><span class="sxs-lookup"><span data-stu-id="83a08-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="83a08-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="83a08-107">array : 'A[]</span></span>

<span data-ttu-id="83a08-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="83a08-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="83a08-109">出力: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="83a08-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="83a08-110">配列の最初の要素と残りのすべての要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="83a08-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="83a08-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="83a08-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="83a08-112">' A</span><span class="sxs-lookup"><span data-stu-id="83a08-112">'A</span></span>

<span data-ttu-id="83a08-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="83a08-113">The type of the array elements.</span></span>