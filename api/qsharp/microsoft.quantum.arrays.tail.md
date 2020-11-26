---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220095"
---
# <a name="tail-function"></a><span data-ttu-id="345c1-102">Tail 関数</span><span class="sxs-lookup"><span data-stu-id="345c1-102">Tail function</span></span>

<span data-ttu-id="345c1-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="345c1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="345c1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="345c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="345c1-105">配列の最後の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="345c1-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="345c1-106">入力</span><span class="sxs-lookup"><span data-stu-id="345c1-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="345c1-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="345c1-107">array : 'A[]</span></span>

<span data-ttu-id="345c1-108">最後の要素が取得された配列。</span><span class="sxs-lookup"><span data-stu-id="345c1-108">Array of which the last element is taken.</span></span> <span data-ttu-id="345c1-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="345c1-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="345c1-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="345c1-110">Output : 'A</span></span>

<span data-ttu-id="345c1-111">配列の最後の要素。</span><span class="sxs-lookup"><span data-stu-id="345c1-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="345c1-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="345c1-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="345c1-113">' A</span><span class="sxs-lookup"><span data-stu-id="345c1-113">'A</span></span>

<span data-ttu-id="345c1-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="345c1-114">The type of the array elements.</span></span>