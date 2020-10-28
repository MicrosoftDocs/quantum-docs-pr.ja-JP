---
uid: Microsoft.Quantum.Arrays.Fold
title: フォールド関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719210"
---
# <a name="fold-function"></a><span data-ttu-id="be74b-102">フォールド関数</span><span class="sxs-lookup"><span data-stu-id="be74b-102">Fold function</span></span>

<span data-ttu-id="be74b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="be74b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="be74b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be74b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be74b-105">配列を使用して関数を反復処理し `f` `array` 、を返し `f(f(f(initialState, array[0]), array[1]), ...)` ます。</span><span class="sxs-lookup"><span data-stu-id="be74b-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="be74b-106">入力</span><span class="sxs-lookup"><span data-stu-id="be74b-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="be74b-107">フォルダー: (' State, ' \)-> ' 状態</span><span class="sxs-lookup"><span data-stu-id="be74b-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="be74b-108">配列に対して折りたたむ関数。</span><span class="sxs-lookup"><span data-stu-id="be74b-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="be74b-109">状態: ' 状態</span><span class="sxs-lookup"><span data-stu-id="be74b-109">state : 'State</span></span>

<span data-ttu-id="be74b-110">フォルダーの初期状態です。</span><span class="sxs-lookup"><span data-stu-id="be74b-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="be74b-111">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="be74b-111">array : 'T[]</span></span>

<span data-ttu-id="be74b-112">折りたたむ値の配列。</span><span class="sxs-lookup"><span data-stu-id="be74b-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="be74b-113">出力: ' 状態</span><span class="sxs-lookup"><span data-stu-id="be74b-113">Output : 'State</span></span>

<span data-ttu-id="be74b-114">のすべての要素を反復処理した後に、フォルダーによって返される最終的な状態 `array` 。</span><span class="sxs-lookup"><span data-stu-id="be74b-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be74b-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="be74b-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="be74b-116">' 状態</span><span class="sxs-lookup"><span data-stu-id="be74b-116">'State</span></span>

<span data-ttu-id="be74b-117">関数が操作する状態の型 `folder` 。つまり、最初の引数としてを受け取り、を返します。</span><span class="sxs-lookup"><span data-stu-id="be74b-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="be74b-118">&</span><span class="sxs-lookup"><span data-stu-id="be74b-118">'T</span></span>

<span data-ttu-id="be74b-119">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="be74b-119">The type of `array` elements.</span></span>