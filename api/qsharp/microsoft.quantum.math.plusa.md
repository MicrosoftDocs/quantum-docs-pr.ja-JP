---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709606"
---
# <a name="plusa-function"></a><span data-ttu-id="e14dd-102">PlusA 関数</span><span class="sxs-lookup"><span data-stu-id="e14dd-102">PlusA function</span></span>

<span data-ttu-id="e14dd-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e14dd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e14dd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e14dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e14dd-105">2つの入力の合計 (連結) を返します。</span><span class="sxs-lookup"><span data-stu-id="e14dd-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="e14dd-106">入力</span><span class="sxs-lookup"><span data-stu-id="e14dd-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="e14dd-107">a: ' Element []</span><span class="sxs-lookup"><span data-stu-id="e14dd-107">a : 'Element[]</span></span>

<span data-ttu-id="e14dd-108">合計する $ $a 最初の入力。</span><span class="sxs-lookup"><span data-stu-id="e14dd-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="e14dd-109">b: ' Element []</span><span class="sxs-lookup"><span data-stu-id="e14dd-109">b : 'Element[]</span></span>

<span data-ttu-id="e14dd-110">合計する $ $b 2 番目の入力。</span><span class="sxs-lookup"><span data-stu-id="e14dd-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="e14dd-111">出力: ' Element []</span><span class="sxs-lookup"><span data-stu-id="e14dd-111">Output : 'Element[]</span></span>

<span data-ttu-id="e14dd-112">合計 $a + b $ です。</span><span class="sxs-lookup"><span data-stu-id="e14dd-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e14dd-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e14dd-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="e14dd-114">' 要素</span><span class="sxs-lookup"><span data-stu-id="e14dd-114">'Element</span></span>

<span data-ttu-id="e14dd-115">2つの入力配列のそれぞれに含まれる各要素の型。</span><span class="sxs-lookup"><span data-stu-id="e14dd-115">The type of each element in each of the two input arrays.</span></span>