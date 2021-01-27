---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: "\"グリーン\" 関数"
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 9f76d5ac47faed9a353db4172cc9037411ab1198
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847315"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="28fdd-102">"グリーン" 関数</span><span class="sxs-lookup"><span data-stu-id="28fdd-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="28fdd-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="28fdd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="28fdd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28fdd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28fdd-105">$A $ と $b $ の最大公約数を計算します。</span><span class="sxs-lookup"><span data-stu-id="28fdd-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="28fdd-106">GCD は常に正の数値です。</span><span class="sxs-lookup"><span data-stu-id="28fdd-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="28fdd-107">入力</span><span class="sxs-lookup"><span data-stu-id="28fdd-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="28fdd-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28fdd-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28fdd-109">拡張された最も一般的な除数の計算対象となる最初の数値</span><span class="sxs-lookup"><span data-stu-id="28fdd-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="28fdd-110">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28fdd-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28fdd-111">拡張された最も一般的な除数が計算されている2番目の数値</span><span class="sxs-lookup"><span data-stu-id="28fdd-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="28fdd-112">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28fdd-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28fdd-113">$a $ と $b $ の最も一般的な除数</span><span class="sxs-lookup"><span data-stu-id="28fdd-113">Greatest common divisor of $a$ and $b$</span></span>