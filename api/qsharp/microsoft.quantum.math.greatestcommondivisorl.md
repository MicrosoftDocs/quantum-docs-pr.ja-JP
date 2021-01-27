---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: グリーンの Stcommon区分 Sorl 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856371"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="69d94-102">グリーンの Stcommon区分 Sorl 関数</span><span class="sxs-lookup"><span data-stu-id="69d94-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="69d94-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="69d94-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="69d94-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69d94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69d94-105">$A $ と $b $ の最大公約数を計算します。</span><span class="sxs-lookup"><span data-stu-id="69d94-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="69d94-106">GCD は常に正の数値です。</span><span class="sxs-lookup"><span data-stu-id="69d94-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="69d94-107">入力</span><span class="sxs-lookup"><span data-stu-id="69d94-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="69d94-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69d94-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69d94-109">拡張された最も一般的な除数の計算対象となる最初の数値</span><span class="sxs-lookup"><span data-stu-id="69d94-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="69d94-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69d94-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69d94-111">拡張された最も一般的な除数が計算されている2番目の数値</span><span class="sxs-lookup"><span data-stu-id="69d94-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="69d94-112">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69d94-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69d94-113">$a $ と $b $ の最も一般的な除数</span><span class="sxs-lookup"><span data-stu-id="69d94-113">Greatest common divisor of $a$ and $b$</span></span>