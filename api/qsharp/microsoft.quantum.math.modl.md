---
uid: Microsoft.Quantum.Math.ModL
title: ModL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723106"
---
# <a name="modl-function"></a><span data-ttu-id="719ca-102">ModL 関数</span><span class="sxs-lookup"><span data-stu-id="719ca-102">ModL function</span></span>

<span data-ttu-id="719ca-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="719ca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="719ca-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="719ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="719ca-105">別の数値に対する数値の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="719ca-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="719ca-106">入力</span><span class="sxs-lookup"><span data-stu-id="719ca-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="719ca-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="719ca-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="719ca-108">剰余が返される入力 $a $。</span><span class="sxs-lookup"><span data-stu-id="719ca-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="719ca-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="719ca-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="719ca-110">$A $ の剰余を返す対象となる数値。</span><span class="sxs-lookup"><span data-stu-id="719ca-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="719ca-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="719ca-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="719ca-112">剰余 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="719ca-112">The modulus $a \bmod b$.</span></span>