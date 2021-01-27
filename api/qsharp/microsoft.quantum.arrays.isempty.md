---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: 1d402b5cfe3a42b47d4ded7064fee06a393772b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845773"
---
# <a name="isempty-function"></a><span data-ttu-id="3944c-102">IsEmpty 関数</span><span class="sxs-lookup"><span data-stu-id="3944c-102">IsEmpty function</span></span>

<span data-ttu-id="3944c-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3944c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3944c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3944c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3944c-105">配列が空の場合にのみ true を返します。</span><span class="sxs-lookup"><span data-stu-id="3944c-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="3944c-106">入力</span><span class="sxs-lookup"><span data-stu-id="3944c-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3944c-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="3944c-107">array : 'T[]</span></span>

<span data-ttu-id="3944c-108">チェックする配列。</span><span class="sxs-lookup"><span data-stu-id="3944c-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3944c-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3944c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3944c-110">`true` 配列が空の場合 (長さが0の場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="3944c-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3944c-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3944c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3944c-112">&</span><span class="sxs-lookup"><span data-stu-id="3944c-112">'T</span></span>

