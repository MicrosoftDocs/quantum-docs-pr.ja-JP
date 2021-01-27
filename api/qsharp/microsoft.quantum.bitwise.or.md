---
uid: Microsoft.Quantum.Bitwise.Or
title: Or 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845281"
---
# <a name="or-function"></a><span data-ttu-id="e7a96-102">Or 関数</span><span class="sxs-lookup"><span data-stu-id="e7a96-102">Or function</span></span>

<span data-ttu-id="e7a96-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="e7a96-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="e7a96-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="e7a96-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e7a96-105">2つの整数のビットごとの OR を返します。</span><span class="sxs-lookup"><span data-stu-id="e7a96-105">Returns the bitwise OR of two integers.</span></span>
<span data-ttu-id="e7a96-106">これにより、組み込み演算子と同じ計算が実行され `|||` ます。</span><span class="sxs-lookup"><span data-stu-id="e7a96-106">This performs the same computation as the built-in `|||` operator.</span></span>

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e7a96-107">入力</span><span class="sxs-lookup"><span data-stu-id="e7a96-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e7a96-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7a96-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="e7a96-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7a96-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="e7a96-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7a96-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="e7a96-111">例</span><span class="sxs-lookup"><span data-stu-id="e7a96-111">Example</span></span>

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a><span data-ttu-id="e7a96-112">解説</span><span class="sxs-lookup"><span data-stu-id="e7a96-112">Remarks</span></span>

<span data-ttu-id="e7a96-113">「C# |」を参照してください。 [演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7a96-113">See the [C# | Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) for more details.</span></span>