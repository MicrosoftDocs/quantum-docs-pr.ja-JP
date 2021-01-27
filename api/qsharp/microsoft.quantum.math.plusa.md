---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842714"
---
# <a name="plusa-function"></a><span data-ttu-id="fcd28-102">PlusA 関数</span><span class="sxs-lookup"><span data-stu-id="fcd28-102">PlusA function</span></span>

<span data-ttu-id="fcd28-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fcd28-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fcd28-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcd28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcd28-105">2つの入力の合計 (連結) を返します。</span><span class="sxs-lookup"><span data-stu-id="fcd28-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="fcd28-106">入力</span><span class="sxs-lookup"><span data-stu-id="fcd28-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="fcd28-107">a: ' Element []</span><span class="sxs-lookup"><span data-stu-id="fcd28-107">a : 'Element[]</span></span>

<span data-ttu-id="fcd28-108">合計する $ $a 最初の入力。</span><span class="sxs-lookup"><span data-stu-id="fcd28-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="fcd28-109">b: ' Element []</span><span class="sxs-lookup"><span data-stu-id="fcd28-109">b : 'Element[]</span></span>

<span data-ttu-id="fcd28-110">合計する $ $b 2 番目の入力。</span><span class="sxs-lookup"><span data-stu-id="fcd28-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="fcd28-111">出力: ' Element []</span><span class="sxs-lookup"><span data-stu-id="fcd28-111">Output : 'Element[]</span></span>

<span data-ttu-id="fcd28-112">合計 $a + b $ です。</span><span class="sxs-lookup"><span data-stu-id="fcd28-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fcd28-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcd28-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="fcd28-114">' 要素</span><span class="sxs-lookup"><span data-stu-id="fcd28-114">'Element</span></span>

<span data-ttu-id="fcd28-115">2つの入力配列のそれぞれに含まれる各要素の型。</span><span class="sxs-lookup"><span data-stu-id="fcd28-115">The type of each element in each of the two input arrays.</span></span>