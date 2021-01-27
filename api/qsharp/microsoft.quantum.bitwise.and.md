---
uid: Microsoft.Quantum.Bitwise.And
title: And 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842161"
---
# <a name="and-function"></a><span data-ttu-id="ea6b0-102">And 関数</span><span class="sxs-lookup"><span data-stu-id="ea6b0-102">And function</span></span>

<span data-ttu-id="ea6b0-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="ea6b0-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="ea6b0-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="ea6b0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ea6b0-105">2つの整数のビットごとの AND を返します。</span><span class="sxs-lookup"><span data-stu-id="ea6b0-105">Returns the bitwise AND of two integers.</span></span>
<span data-ttu-id="ea6b0-106">これにより、組み込み演算子と同じ計算が実行され `&&&` ます。</span><span class="sxs-lookup"><span data-stu-id="ea6b0-106">This performs the same computation as the built-in `&&&` operator.</span></span>

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ea6b0-107">入力</span><span class="sxs-lookup"><span data-stu-id="ea6b0-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ea6b0-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea6b0-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="ea6b0-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea6b0-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="ea6b0-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea6b0-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="ea6b0-111">例</span><span class="sxs-lookup"><span data-stu-id="ea6b0-111">Example</span></span>

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a><span data-ttu-id="ea6b0-112">解説</span><span class="sxs-lookup"><span data-stu-id="ea6b0-112">Remarks</span></span>

<span data-ttu-id="ea6b0-113">詳細については、「 [C# &amp; 演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (バイナリ)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea6b0-113">See the [C# &amp; Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binary) for more details.</span></span>