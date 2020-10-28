---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: f658c2a25b6991d9a826706a7e95b68169901f0e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719114"
---
# <a name="isempty-function"></a><span data-ttu-id="c4e05-102">IsEmpty 関数</span><span class="sxs-lookup"><span data-stu-id="c4e05-102">IsEmpty function</span></span>

<span data-ttu-id="c4e05-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4e05-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4e05-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4e05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4e05-105">配列が空の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="c4e05-106">入力</span><span class="sxs-lookup"><span data-stu-id="c4e05-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c4e05-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="c4e05-107">array : 'T[]</span></span>

<span data-ttu-id="c4e05-108">チェックする配列。</span><span class="sxs-lookup"><span data-stu-id="c4e05-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c4e05-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4e05-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4e05-110">`true` 配列が空の場合 (長さが0の場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="c4e05-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4e05-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4e05-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4e05-112">&</span><span class="sxs-lookup"><span data-stu-id="c4e05-112">'T</span></span>

