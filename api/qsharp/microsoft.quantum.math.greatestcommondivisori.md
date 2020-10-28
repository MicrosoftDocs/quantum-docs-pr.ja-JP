---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: "\"グリーン\" 関数"
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723652"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="dd2ce-102">"グリーン" 関数</span><span class="sxs-lookup"><span data-stu-id="dd2ce-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="dd2ce-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dd2ce-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dd2ce-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd2ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd2ce-105">$A $ と $b $ の最大公約数を計算します。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="dd2ce-106">GCD は常に正の数値です。</span><span class="sxs-lookup"><span data-stu-id="dd2ce-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="dd2ce-107">入力</span><span class="sxs-lookup"><span data-stu-id="dd2ce-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd2ce-108">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd2ce-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd2ce-109">拡張された最も一般的な除数の計算対象となる最初の数値</span><span class="sxs-lookup"><span data-stu-id="dd2ce-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="dd2ce-110">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd2ce-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd2ce-111">拡張された最も一般的な除数が計算されている2番目の数値</span><span class="sxs-lookup"><span data-stu-id="dd2ce-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="dd2ce-112">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd2ce-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd2ce-113">$a $ と $b $ の最も一般的な除数</span><span class="sxs-lookup"><span data-stu-id="dd2ce-113">Greatest common divisor of $a$ and $b$</span></span>