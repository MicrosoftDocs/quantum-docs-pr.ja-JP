---
uid: Microsoft.Quantum.Math.ModL
title: ModL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846839"
---
# <a name="modl-function"></a><span data-ttu-id="de526-102">ModL 関数</span><span class="sxs-lookup"><span data-stu-id="de526-102">ModL function</span></span>

<span data-ttu-id="de526-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="de526-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="de526-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de526-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de526-105">別の数値に対する数値の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="de526-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="de526-106">入力</span><span class="sxs-lookup"><span data-stu-id="de526-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="de526-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="de526-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="de526-108">剰余が返される入力 $a $。</span><span class="sxs-lookup"><span data-stu-id="de526-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="de526-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="de526-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="de526-110">$A $ の剰余を返す対象となる数値。</span><span class="sxs-lookup"><span data-stu-id="de526-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="de526-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="de526-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="de526-112">剰余 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="de526-112">The modulus $a \bmod b$.</span></span>