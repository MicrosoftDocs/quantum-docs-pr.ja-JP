---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848345"
---
# <a name="realmod-function"></a><span data-ttu-id="a5279-102">RealMod 関数</span><span class="sxs-lookup"><span data-stu-id="a5279-102">RealMod function</span></span>

<span data-ttu-id="a5279-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a5279-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a5279-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5279-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5279-105">2つの実数の間の剰余を計算します。</span><span class="sxs-lookup"><span data-stu-id="a5279-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="a5279-106">入力</span><span class="sxs-lookup"><span data-stu-id="a5279-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="a5279-107">値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5279-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5279-108">の剰余を取得するための実数 ($ $x)。</span><span class="sxs-lookup"><span data-stu-id="a5279-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="a5279-109">剰余: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5279-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5279-110">に関して $x $ の剰余を取得する実数。</span><span class="sxs-lookup"><span data-stu-id="a5279-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="a5279-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5279-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5279-112">この関数によって返される最小値。</span><span class="sxs-lookup"><span data-stu-id="a5279-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="a5279-113">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5279-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="a5279-114">例</span><span class="sxs-lookup"><span data-stu-id="a5279-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="a5279-115">解説</span><span class="sxs-lookup"><span data-stu-id="a5279-115">Remarks</span></span>

<span data-ttu-id="a5279-116">この関数は、単位の円に関する実際の線をラップし、入力に対応する単位の円の角度を検索することによって、実数の剰余を計算します。</span><span class="sxs-lookup"><span data-stu-id="a5279-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="a5279-117">入力によって、 `minValue` 実際には、単位の円を切り取る場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="a5279-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>