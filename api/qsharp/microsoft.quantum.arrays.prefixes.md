---
uid: Microsoft.Quantum.Arrays.Prefixes
title: プレフィックス関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845503"
---
# <a name="prefixes-function"></a><span data-ttu-id="d0407-102">プレフィックス関数</span><span class="sxs-lookup"><span data-stu-id="d0407-102">Prefixes function</span></span>

<span data-ttu-id="d0407-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0407-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0407-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0407-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0407-105">配列を指定すると、そのすべてのプレフィックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="d0407-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="d0407-106">説明</span><span class="sxs-lookup"><span data-stu-id="d0407-106">Description</span></span>

<span data-ttu-id="d0407-107">すべてのプレフィックスの配列を返します。最初の要素が配列全体になるまで、最初の要素のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0407-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="d0407-108">入力</span><span class="sxs-lookup"><span data-stu-id="d0407-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d0407-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="d0407-109">array : 'T[]</span></span>

<span data-ttu-id="d0407-110">要素の配列。</span><span class="sxs-lookup"><span data-stu-id="d0407-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0407-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="d0407-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0407-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0407-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0407-113">&</span><span class="sxs-lookup"><span data-stu-id="d0407-113">'T</span></span>

<span data-ttu-id="d0407-114">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d0407-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="d0407-115">例</span><span class="sxs-lookup"><span data-stu-id="d0407-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```