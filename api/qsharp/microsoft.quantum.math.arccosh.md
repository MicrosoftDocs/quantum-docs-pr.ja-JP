---
uid: Microsoft.Quantum.Math.ArcCosh
title: ArcCosh 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArcCosh
qsharp.summary: Computes the inverse hyperbolic cosine of a number.
ms.openlocfilehash: 5598e45f7cc34cdc686b26655c267a06b8476db0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848964"
---
# <a name="arccosh-function"></a><span data-ttu-id="90cc0-102">ArcCosh 関数</span><span class="sxs-lookup"><span data-stu-id="90cc0-102">ArcCosh function</span></span>

<span data-ttu-id="90cc0-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90cc0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90cc0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90cc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90cc0-105">数値の逆双曲線余弦を計算します。</span><span class="sxs-lookup"><span data-stu-id="90cc0-105">Computes the inverse hyperbolic cosine of a number.</span></span>

```qsharp
function ArcCosh (x : Double) : Double
```


## <a name="input"></a><span data-ttu-id="90cc0-106">入力</span><span class="sxs-lookup"><span data-stu-id="90cc0-106">Input</span></span>

### <a name="x--double"></a><span data-ttu-id="90cc0-107">x: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90cc0-107">x : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90cc0-108">実際の数値 $x \ geq $1。</span><span class="sxs-lookup"><span data-stu-id="90cc0-108">A real number $x\geq 1$.</span></span>



## <a name="output--double"></a><span data-ttu-id="90cc0-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90cc0-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90cc0-110">$X = \cosh (y) $ である $y $ の実数。</span><span class="sxs-lookup"><span data-stu-id="90cc0-110">A real number $y$ such that $x = \cosh(y)$.</span></span>