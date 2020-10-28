---
uid: Microsoft.Quantum.Math.ModI
title: ModI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: d5581c5e2e4f0bcb4f8eec78464292e23031155c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723111"
---
# <a name="modi-function"></a><span data-ttu-id="6ac44-102">ModI 関数</span><span class="sxs-lookup"><span data-stu-id="6ac44-102">ModI function</span></span>

<span data-ttu-id="6ac44-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ac44-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ac44-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ac44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ac44-105">別の数値に対する数値の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="6ac44-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6ac44-106">入力</span><span class="sxs-lookup"><span data-stu-id="6ac44-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6ac44-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ac44-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ac44-108">剰余が返される入力 $a $。</span><span class="sxs-lookup"><span data-stu-id="6ac44-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="6ac44-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ac44-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ac44-110">$A $ の剰余を返す対象となる数値。</span><span class="sxs-lookup"><span data-stu-id="6ac44-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="6ac44-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ac44-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ac44-112">剰余 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="6ac44-112">The modulus $a \bmod b$.</span></span>