---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848569"
---
# <a name="head-function"></a><span data-ttu-id="a0c01-102">Head 関数</span><span class="sxs-lookup"><span data-stu-id="a0c01-102">Head function</span></span>

<span data-ttu-id="a0c01-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0c01-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0c01-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0c01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0c01-105">配列の最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="a0c01-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="a0c01-106">入力</span><span class="sxs-lookup"><span data-stu-id="a0c01-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a0c01-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="a0c01-107">array : 'A[]</span></span>

<span data-ttu-id="a0c01-108">最初の要素を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="a0c01-108">Array of which the first element is taken.</span></span> <span data-ttu-id="a0c01-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c01-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="a0c01-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="a0c01-110">Output : 'A</span></span>

<span data-ttu-id="a0c01-111">配列の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="a0c01-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0c01-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0c01-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a0c01-113">' A</span><span class="sxs-lookup"><span data-stu-id="a0c01-113">'A</span></span>

<span data-ttu-id="a0c01-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="a0c01-114">The type of the array elements.</span></span>