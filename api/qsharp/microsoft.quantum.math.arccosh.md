---
uid: Microsoft.Quantum.Math.ArcCosh
title: ArcCosh 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArcCosh
qsharp.summary: Computes the inverse hyperbolic cosine of a number.
ms.openlocfilehash: bbf3b63668b0e676dafe1d146d4b30c48dc20f41
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723279"
---
# <a name="arccosh-function"></a><span data-ttu-id="53792-102">ArcCosh 関数</span><span class="sxs-lookup"><span data-stu-id="53792-102">ArcCosh function</span></span>

<span data-ttu-id="53792-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="53792-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="53792-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53792-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53792-105">数値の逆双曲線余弦を計算します。</span><span class="sxs-lookup"><span data-stu-id="53792-105">Computes the inverse hyperbolic cosine of a number.</span></span>

```qsharp
function ArcCosh (x : Double) : Double
```


## <a name="input"></a><span data-ttu-id="53792-106">入力</span><span class="sxs-lookup"><span data-stu-id="53792-106">Input</span></span>

### <a name="x--double"></a><span data-ttu-id="53792-107">x: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53792-107">x : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53792-108">実際の数値 $x \ geq $1。</span><span class="sxs-lookup"><span data-stu-id="53792-108">A real number $x\geq 1$.</span></span>



## <a name="output--double"></a><span data-ttu-id="53792-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53792-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53792-110">$X = \cosh (y) $ である $y $ の実数。</span><span class="sxs-lookup"><span data-stu-id="53792-110">A real number $y$ such that $x = \cosh(y)$.</span></span>