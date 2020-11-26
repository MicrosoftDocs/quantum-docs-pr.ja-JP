---
uid: Microsoft.Quantum.Math.ModI
title: ModI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: e0d735096ce00b97ac42b336ac226e8e25879c94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195020"
---
# <a name="modi-function"></a><span data-ttu-id="91f47-102">ModI 関数</span><span class="sxs-lookup"><span data-stu-id="91f47-102">ModI function</span></span>

<span data-ttu-id="91f47-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="91f47-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="91f47-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91f47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91f47-105">別の数値に対する数値の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="91f47-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="91f47-106">入力</span><span class="sxs-lookup"><span data-stu-id="91f47-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="91f47-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f47-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91f47-108">剰余が返される入力 $a $。</span><span class="sxs-lookup"><span data-stu-id="91f47-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="91f47-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f47-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91f47-110">$A $ の剰余を返す対象となる数値。</span><span class="sxs-lookup"><span data-stu-id="91f47-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="91f47-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f47-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91f47-112">剰余 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="91f47-112">The modulus $a \bmod b$.</span></span>