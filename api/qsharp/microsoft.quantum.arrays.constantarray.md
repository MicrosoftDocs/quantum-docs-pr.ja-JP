---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719414"
---
# <a name="constantarray-function"></a><span data-ttu-id="7d44a-102">ConstantArray 関数</span><span class="sxs-lookup"><span data-stu-id="7d44a-102">ConstantArray function</span></span>

<span data-ttu-id="7d44a-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7d44a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7d44a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d44a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d44a-105">指定された値と等しいすべての要素を使用して、指定された長さの配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d44a-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7d44a-106">入力</span><span class="sxs-lookup"><span data-stu-id="7d44a-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="7d44a-107">長さ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d44a-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d44a-108">新しい配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="7d44a-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="7d44a-109">値: ' t '</span><span class="sxs-lookup"><span data-stu-id="7d44a-109">value : 'T</span></span>

<span data-ttu-id="7d44a-110">新しい配列の各要素の値。</span><span class="sxs-lookup"><span data-stu-id="7d44a-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="7d44a-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="7d44a-111">Output : 'T[]</span></span>

<span data-ttu-id="7d44a-112">`length`すべての要素がである、長さの新しい配列 `value` 。</span><span class="sxs-lookup"><span data-stu-id="7d44a-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7d44a-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d44a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d44a-114">&</span><span class="sxs-lookup"><span data-stu-id="7d44a-114">'T</span></span>

