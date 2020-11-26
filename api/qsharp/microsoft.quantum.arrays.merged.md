---
uid: Microsoft.Quantum.Arrays.Merged
title: マージされた関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220639"
---
# <a name="merged-function"></a><span data-ttu-id="43394-102">マージされた関数</span><span class="sxs-lookup"><span data-stu-id="43394-102">Merged function</span></span>

<span data-ttu-id="43394-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43394-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43394-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43394-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43394-105">2つの並べ替えられた配列を指定した場合、両方のの要素が並べ替えられた順序で格納された単一の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="43394-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="43394-106">Merge sort によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="43394-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="43394-107">入力</span><span class="sxs-lookup"><span data-stu-id="43394-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="43394-108">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="43394-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="43394-109">左: \ []</span><span class="sxs-lookup"><span data-stu-id="43394-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="43394-110">right: t []</span><span class="sxs-lookup"><span data-stu-id="43394-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="43394-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="43394-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43394-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="43394-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43394-113">&</span><span class="sxs-lookup"><span data-stu-id="43394-113">'T</span></span>

