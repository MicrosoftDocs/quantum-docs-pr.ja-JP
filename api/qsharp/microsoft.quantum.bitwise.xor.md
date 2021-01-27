---
uid: Microsoft.Quantum.Bitwise.Xor
title: Xor 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842079"
---
# <a name="xor-function"></a><span data-ttu-id="9ab29-102">Xor 関数</span><span class="sxs-lookup"><span data-stu-id="9ab29-102">Xor function</span></span>

<span data-ttu-id="9ab29-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="9ab29-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="9ab29-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="9ab29-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9ab29-105">2つの整数のビットごとの排他的 OR (XOR) を返します。</span><span class="sxs-lookup"><span data-stu-id="9ab29-105">Returns the bitwise exclusive-OR (XOR) of two integers.</span></span>
<span data-ttu-id="9ab29-106">これにより、組み込み演算子と同じ計算が実行され `^^^` ます。</span><span class="sxs-lookup"><span data-stu-id="9ab29-106">This performs the same computation as the built-in `^^^` operator.</span></span>

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="9ab29-107">入力</span><span class="sxs-lookup"><span data-stu-id="9ab29-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9ab29-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ab29-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="9ab29-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ab29-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="9ab29-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ab29-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="9ab29-111">例</span><span class="sxs-lookup"><span data-stu-id="9ab29-111">Example</span></span>

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a><span data-ttu-id="9ab29-112">解説</span><span class="sxs-lookup"><span data-stu-id="9ab29-112">Remarks</span></span>

<span data-ttu-id="9ab29-113">詳細については、「 [C# ^ 演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ab29-113">See the [C# ^ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) for more details.</span></span>