---
uid: Microsoft.Quantum.Arrays.Swapped
title: スワップした関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850950"
---
# <a name="swapped-function"></a><span data-ttu-id="fa011-102">スワップした関数</span><span class="sxs-lookup"><span data-stu-id="fa011-102">Swapped function</span></span>

<span data-ttu-id="fa011-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa011-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa011-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa011-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa011-105">配列内の2つの要素のスワップを適用します。</span><span class="sxs-lookup"><span data-stu-id="fa011-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fa011-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa011-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="fa011-107">firstIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa011-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa011-108">交換される最初の要素のインデックス。</span><span class="sxs-lookup"><span data-stu-id="fa011-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="fa011-109">次のインデックス: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa011-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa011-110">スワップする2番目の要素のインデックス。</span><span class="sxs-lookup"><span data-stu-id="fa011-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="fa011-111">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="fa011-111">arr : 'T[]</span></span>

<span data-ttu-id="fa011-112">交換する要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="fa011-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="fa011-113">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="fa011-113">Output : 'T[]</span></span>

<span data-ttu-id="fa011-114">インプレーススワップが適用された配列。</span><span class="sxs-lookup"><span data-stu-id="fa011-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="fa011-115">例</span><span class="sxs-lookup"><span data-stu-id="fa011-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="fa011-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa011-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa011-117">&</span><span class="sxs-lookup"><span data-stu-id="fa011-117">'T</span></span>

