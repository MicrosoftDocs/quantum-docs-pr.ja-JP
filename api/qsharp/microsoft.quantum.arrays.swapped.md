---
uid: Microsoft.Quantum.Arrays.Swapped
title: スワップした関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718826"
---
# <a name="swapped-function"></a><span data-ttu-id="7b542-102">スワップした関数</span><span class="sxs-lookup"><span data-stu-id="7b542-102">Swapped function</span></span>

<span data-ttu-id="7b542-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7b542-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7b542-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b542-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b542-105">配列内の2つの要素のスワップを適用します。</span><span class="sxs-lookup"><span data-stu-id="7b542-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7b542-106">入力</span><span class="sxs-lookup"><span data-stu-id="7b542-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="7b542-107">firstIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b542-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b542-108">交換される最初の要素のインデックス。</span><span class="sxs-lookup"><span data-stu-id="7b542-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="7b542-109">次のインデックス: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b542-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b542-110">スワップする2番目の要素のインデックス。</span><span class="sxs-lookup"><span data-stu-id="7b542-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="7b542-111">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="7b542-111">arr : 'T[]</span></span>

<span data-ttu-id="7b542-112">交換する要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="7b542-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="7b542-113">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="7b542-113">Output : 'T[]</span></span>

<span data-ttu-id="7b542-114">インプレーススワップが適用された配列。</span><span class="sxs-lookup"><span data-stu-id="7b542-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="7b542-115">例</span><span class="sxs-lookup"><span data-stu-id="7b542-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="7b542-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b542-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b542-117">&</span><span class="sxs-lookup"><span data-stu-id="7b542-117">'T</span></span>

