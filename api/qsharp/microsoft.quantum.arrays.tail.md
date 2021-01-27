---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845411"
---
# <a name="tail-function"></a><span data-ttu-id="7c26e-102">Tail 関数</span><span class="sxs-lookup"><span data-stu-id="7c26e-102">Tail function</span></span>

<span data-ttu-id="7c26e-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7c26e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7c26e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c26e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c26e-105">配列の最後の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="7c26e-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="7c26e-106">入力</span><span class="sxs-lookup"><span data-stu-id="7c26e-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="7c26e-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="7c26e-107">array : 'A[]</span></span>

<span data-ttu-id="7c26e-108">最後の要素が取得された配列。</span><span class="sxs-lookup"><span data-stu-id="7c26e-108">Array of which the last element is taken.</span></span> <span data-ttu-id="7c26e-109">配列の長さは少なくとも1である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c26e-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="7c26e-110">出力: ' A</span><span class="sxs-lookup"><span data-stu-id="7c26e-110">Output : 'A</span></span>

<span data-ttu-id="7c26e-111">配列の最後の要素。</span><span class="sxs-lookup"><span data-stu-id="7c26e-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7c26e-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c26e-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="7c26e-113">' A</span><span class="sxs-lookup"><span data-stu-id="7c26e-113">'A</span></span>

<span data-ttu-id="7c26e-114">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="7c26e-114">The type of the array elements.</span></span>