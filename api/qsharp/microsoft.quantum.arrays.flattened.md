---
uid: Microsoft.Quantum.Arrays.Flattened
title: フラット化関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719239"
---
# <a name="flattened-function"></a><span data-ttu-id="97af5-102">フラット化関数</span><span class="sxs-lookup"><span data-stu-id="97af5-102">Flattened function</span></span>

<span data-ttu-id="97af5-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="97af5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="97af5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97af5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97af5-105">配列の配列を指定すると、すべての配列の連結が返されます。</span><span class="sxs-lookup"><span data-stu-id="97af5-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="97af5-106">入力</span><span class="sxs-lookup"><span data-stu-id="97af5-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="97af5-107">配列: t [] []</span><span class="sxs-lookup"><span data-stu-id="97af5-107">arrays : 'T[][]</span></span>

<span data-ttu-id="97af5-108">配列の配列。</span><span class="sxs-lookup"><span data-stu-id="97af5-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="97af5-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="97af5-109">Output : 'T[]</span></span>

<span data-ttu-id="97af5-110">すべての配列の連結。</span><span class="sxs-lookup"><span data-stu-id="97af5-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="97af5-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="97af5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="97af5-112">&</span><span class="sxs-lookup"><span data-stu-id="97af5-112">'T</span></span>

<span data-ttu-id="97af5-113">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="97af5-113">The type of `array` elements.</span></span>