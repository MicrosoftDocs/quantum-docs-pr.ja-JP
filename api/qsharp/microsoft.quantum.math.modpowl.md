---
uid: Microsoft.Quantum.Math.ModPowL
title: ModPowL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModPowL
qsharp.summary: Performs modular division on a number raised to the power of another number.
ms.openlocfilehash: 7d3e1de8c7d0eb5f35392bec373e7f16b152ca3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723083"
---
# <a name="modpowl-function"></a><span data-ttu-id="15900-102">ModPowL 関数</span><span class="sxs-lookup"><span data-stu-id="15900-102">ModPowL function</span></span>

<span data-ttu-id="15900-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="15900-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="15900-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15900-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15900-105">別の数値のべき乗で累乗された数値でモジュール分割を実行します。</span><span class="sxs-lookup"><span data-stu-id="15900-105">Performs modular division on a number raised to the power of another number.</span></span>

```qsharp
function ModPowL (value : BigInt, exponent : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="15900-106">入力</span><span class="sxs-lookup"><span data-stu-id="15900-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="15900-107">値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15900-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="exponent--bigint"></a><span data-ttu-id="15900-108">指数: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15900-108">exponent : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="15900-109">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15900-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="15900-110">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15900-110">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="15900-111">解説</span><span class="sxs-lookup"><span data-stu-id="15900-111">Remarks</span></span>

<span data-ttu-id="15900-112">詳細については、 [BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.modpow) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15900-112">See [System.Numerics.BigInteger.ModPow](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.modpow) for more details.</span></span>