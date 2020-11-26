---
uid: Microsoft.Quantum.Math.ArcCosh
title: ArcCosh 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArcCosh
qsharp.summary: Computes the inverse hyperbolic cosine of a number.
ms.openlocfilehash: a919cd200b378e22aaef609e3c89ba39f3338042
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211221"
---
# <a name="arccosh-function"></a><span data-ttu-id="2f150-102">ArcCosh 関数</span><span class="sxs-lookup"><span data-stu-id="2f150-102">ArcCosh function</span></span>

<span data-ttu-id="2f150-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2f150-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2f150-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f150-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f150-105">数値の逆双曲線余弦を計算します。</span><span class="sxs-lookup"><span data-stu-id="2f150-105">Computes the inverse hyperbolic cosine of a number.</span></span>

```qsharp
function ArcCosh (x : Double) : Double
```


## <a name="input"></a><span data-ttu-id="2f150-106">入力</span><span class="sxs-lookup"><span data-stu-id="2f150-106">Input</span></span>

### <a name="x--double"></a><span data-ttu-id="2f150-107">x: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f150-107">x : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f150-108">実際の数値 $x \ geq $1。</span><span class="sxs-lookup"><span data-stu-id="2f150-108">A real number $x\geq 1$.</span></span>



## <a name="output--double"></a><span data-ttu-id="2f150-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f150-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f150-110">$X = \cosh (y) $ である $y $ の実数。</span><span class="sxs-lookup"><span data-stu-id="2f150-110">A real number $y$ such that $x = \cosh(y)$.</span></span>