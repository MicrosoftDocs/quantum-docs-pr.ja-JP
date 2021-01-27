---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842108"
---
# <a name="not-function"></a><span data-ttu-id="59ea6-102">Not 関数</span><span class="sxs-lookup"><span data-stu-id="59ea6-102">Not function</span></span>

<span data-ttu-id="59ea6-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="59ea6-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="59ea6-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="59ea6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="59ea6-105">整数のビットごとの NOT を返します。</span><span class="sxs-lookup"><span data-stu-id="59ea6-105">Returns the bitwise NOT of an integer.</span></span>
<span data-ttu-id="59ea6-106">これにより、組み込み演算子と同じ計算が実行され `~~~` ます。</span><span class="sxs-lookup"><span data-stu-id="59ea6-106">This performs the same computation as the built-in `~~~` operator.</span></span>

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="59ea6-107">入力</span><span class="sxs-lookup"><span data-stu-id="59ea6-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="59ea6-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59ea6-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="59ea6-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59ea6-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="59ea6-110">例</span><span class="sxs-lookup"><span data-stu-id="59ea6-110">Example</span></span>

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a><span data-ttu-id="59ea6-111">解説</span><span class="sxs-lookup"><span data-stu-id="59ea6-111">Remarks</span></span>

<span data-ttu-id="59ea6-112">詳細については、「 [~ 演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59ea6-112">See the [C# ~ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) for more details.</span></span>