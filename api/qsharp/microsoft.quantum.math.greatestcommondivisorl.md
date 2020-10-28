---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: グリーンの Stcommon区分 Sorl 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723643"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="9ac19-102">グリーンの Stcommon区分 Sorl 関数</span><span class="sxs-lookup"><span data-stu-id="9ac19-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="9ac19-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9ac19-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9ac19-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ac19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ac19-105">$A $ と $b $ の最大公約数を計算します。</span><span class="sxs-lookup"><span data-stu-id="9ac19-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="9ac19-106">GCD は常に正の数値です。</span><span class="sxs-lookup"><span data-stu-id="9ac19-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="9ac19-107">入力</span><span class="sxs-lookup"><span data-stu-id="9ac19-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9ac19-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9ac19-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9ac19-109">拡張された最も一般的な除数の計算対象となる最初の数値</span><span class="sxs-lookup"><span data-stu-id="9ac19-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9ac19-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9ac19-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9ac19-111">拡張された最も一般的な除数が計算されている2番目の数値</span><span class="sxs-lookup"><span data-stu-id="9ac19-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9ac19-112">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9ac19-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9ac19-113">$a $ と $b $ の最も一般的な除数</span><span class="sxs-lookup"><span data-stu-id="9ac19-113">Greatest common divisor of $a$ and $b$</span></span>