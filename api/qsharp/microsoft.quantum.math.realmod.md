---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228255"
---
# <a name="realmod-function"></a><span data-ttu-id="bde4a-102">RealMod 関数</span><span class="sxs-lookup"><span data-stu-id="bde4a-102">RealMod function</span></span>

<span data-ttu-id="bde4a-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bde4a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bde4a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bde4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bde4a-105">2つの実数の間の剰余を計算します。</span><span class="sxs-lookup"><span data-stu-id="bde4a-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="bde4a-106">入力</span><span class="sxs-lookup"><span data-stu-id="bde4a-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="bde4a-107">値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bde4a-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bde4a-108">の剰余を取得するための実数 ($ $x)。</span><span class="sxs-lookup"><span data-stu-id="bde4a-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="bde4a-109">剰余: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bde4a-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bde4a-110">に関して $x $ の剰余を取得する実数。</span><span class="sxs-lookup"><span data-stu-id="bde4a-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="bde4a-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bde4a-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bde4a-112">この関数によって返される最小値。</span><span class="sxs-lookup"><span data-stu-id="bde4a-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="bde4a-113">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bde4a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="bde4a-114">解説</span><span class="sxs-lookup"><span data-stu-id="bde4a-114">Remarks</span></span>

<span data-ttu-id="bde4a-115">この関数は、単位の円に関する実際の線をラップし、入力に対応する単位の円の角度を検索することによって、実数の剰余を計算します。</span><span class="sxs-lookup"><span data-stu-id="bde4a-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="bde4a-116">入力によって、 `minValue` 実際には、単位の円を切り取る場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="bde4a-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>