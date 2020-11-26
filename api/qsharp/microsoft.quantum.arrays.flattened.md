---
uid: Microsoft.Quantum.Arrays.Flattened
title: フラット化関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221217"
---
# <a name="flattened-function"></a><span data-ttu-id="7cde2-102">フラット化関数</span><span class="sxs-lookup"><span data-stu-id="7cde2-102">Flattened function</span></span>

<span data-ttu-id="7cde2-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7cde2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7cde2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7cde2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7cde2-105">配列の配列を指定すると、すべての配列の連結が返されます。</span><span class="sxs-lookup"><span data-stu-id="7cde2-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7cde2-106">入力</span><span class="sxs-lookup"><span data-stu-id="7cde2-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="7cde2-107">配列: t [] []</span><span class="sxs-lookup"><span data-stu-id="7cde2-107">arrays : 'T[][]</span></span>

<span data-ttu-id="7cde2-108">配列の配列。</span><span class="sxs-lookup"><span data-stu-id="7cde2-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="7cde2-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="7cde2-109">Output : 'T[]</span></span>

<span data-ttu-id="7cde2-110">すべての配列の連結。</span><span class="sxs-lookup"><span data-stu-id="7cde2-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7cde2-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cde2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cde2-112">&</span><span class="sxs-lookup"><span data-stu-id="7cde2-112">'T</span></span>

<span data-ttu-id="7cde2-113">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7cde2-113">The type of `array` elements.</span></span>