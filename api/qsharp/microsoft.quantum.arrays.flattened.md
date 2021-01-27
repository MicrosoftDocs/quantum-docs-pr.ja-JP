---
uid: Microsoft.Quantum.Arrays.Flattened
title: フラット化関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848626"
---
# <a name="flattened-function"></a><span data-ttu-id="95f8f-102">フラット化関数</span><span class="sxs-lookup"><span data-stu-id="95f8f-102">Flattened function</span></span>

<span data-ttu-id="95f8f-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95f8f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95f8f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95f8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95f8f-105">配列の配列を指定すると、すべての配列の連結が返されます。</span><span class="sxs-lookup"><span data-stu-id="95f8f-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="95f8f-106">入力</span><span class="sxs-lookup"><span data-stu-id="95f8f-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="95f8f-107">配列: t [] []</span><span class="sxs-lookup"><span data-stu-id="95f8f-107">arrays : 'T[][]</span></span>

<span data-ttu-id="95f8f-108">配列の配列。</span><span class="sxs-lookup"><span data-stu-id="95f8f-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="95f8f-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="95f8f-109">Output : 'T[]</span></span>

<span data-ttu-id="95f8f-110">すべての配列の連結。</span><span class="sxs-lookup"><span data-stu-id="95f8f-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95f8f-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="95f8f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95f8f-112">&</span><span class="sxs-lookup"><span data-stu-id="95f8f-112">'T</span></span>

<span data-ttu-id="95f8f-113">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="95f8f-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="95f8f-114">例</span><span class="sxs-lookup"><span data-stu-id="95f8f-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```