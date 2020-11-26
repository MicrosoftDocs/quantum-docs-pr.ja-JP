---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210065"
---
# <a name="constantarray-function"></a><span data-ttu-id="cbad7-102">ConstantArray 関数</span><span class="sxs-lookup"><span data-stu-id="cbad7-102">ConstantArray function</span></span>

<span data-ttu-id="cbad7-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cbad7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cbad7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbad7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbad7-105">指定された値と等しいすべての要素を使用して、指定された長さの配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="cbad7-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cbad7-106">入力</span><span class="sxs-lookup"><span data-stu-id="cbad7-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="cbad7-107">長さ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbad7-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbad7-108">新しい配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="cbad7-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="cbad7-109">値: ' t '</span><span class="sxs-lookup"><span data-stu-id="cbad7-109">value : 'T</span></span>

<span data-ttu-id="cbad7-110">新しい配列の各要素の値。</span><span class="sxs-lookup"><span data-stu-id="cbad7-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="cbad7-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="cbad7-111">Output : 'T[]</span></span>

<span data-ttu-id="cbad7-112">`length`すべての要素がである、長さの新しい配列 `value` 。</span><span class="sxs-lookup"><span data-stu-id="cbad7-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cbad7-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbad7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cbad7-114">&</span><span class="sxs-lookup"><span data-stu-id="cbad7-114">'T</span></span>

