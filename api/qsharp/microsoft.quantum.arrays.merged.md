---
uid: Microsoft.Quantum.Arrays.Merged
title: マージされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719011"
---
# <a name="merged-function"></a><span data-ttu-id="c333a-102">マージされた関数</span><span class="sxs-lookup"><span data-stu-id="c333a-102">Merged function</span></span>

<span data-ttu-id="c333a-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c333a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c333a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c333a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c333a-105">2つの並べ替えられた配列を指定した場合、両方のの要素が並べ替えられた順序で格納された単一の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="c333a-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="c333a-106">Merge sort によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c333a-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c333a-107">入力</span><span class="sxs-lookup"><span data-stu-id="c333a-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="c333a-108">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c333a-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="c333a-109">左: \ []</span><span class="sxs-lookup"><span data-stu-id="c333a-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="c333a-110">right: t []</span><span class="sxs-lookup"><span data-stu-id="c333a-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="c333a-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="c333a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c333a-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c333a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c333a-113">&</span><span class="sxs-lookup"><span data-stu-id="c333a-113">'T</span></span>

