---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221115"
---
# <a name="head-function"></a><span data-ttu-id="4c044-102">Head 関数</span><span class="sxs-lookup"><span data-stu-id="4c044-102">Head function</span></span>

<span data-ttu-id="4c044-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4c044-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4c044-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c044-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c044-105">配列の最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="4c044-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="4c044-106">入力</span><span class="sxs-lookup"><span data-stu-id="4c044-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="4c044-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="4c044-107">array : 'A[]</span></span>

<span data-ttu-id="4c044-108">最初の要素を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="4c044-108">Array of which the first element is taken.</span></span> <span data-ttu-id="4c044-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c044-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="4c044-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="4c044-110">Output : 'A</span></span>

<span data-ttu-id="4c044-111">配列の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="4c044-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4c044-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c044-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="4c044-113">' A</span><span class="sxs-lookup"><span data-stu-id="4c044-113">'A</span></span>

<span data-ttu-id="4c044-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="4c044-114">The type of the array elements.</span></span>