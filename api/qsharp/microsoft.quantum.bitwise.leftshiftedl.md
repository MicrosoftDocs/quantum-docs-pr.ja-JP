---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718634"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="33b39-102">LeftShiftedL 関数</span><span class="sxs-lookup"><span data-stu-id="33b39-102">LeftShiftedL function</span></span>

<span data-ttu-id="33b39-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="33b39-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="33b39-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33b39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33b39-105">指定されたビット数だけ左にある数値のビットごとの表現をシフトします。</span><span class="sxs-lookup"><span data-stu-id="33b39-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="33b39-106">入力</span><span class="sxs-lookup"><span data-stu-id="33b39-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="33b39-107">値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="33b39-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="33b39-108">ビットごとの表現を左にシフトする数値 (より大きい)。</span><span class="sxs-lookup"><span data-stu-id="33b39-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="33b39-109">amount: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33b39-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33b39-110">を左にシフトするときに使用するビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="33b39-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="33b39-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="33b39-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="33b39-112">ビットで左にシフトされたの値 `value` `amount` 。</span><span class="sxs-lookup"><span data-stu-id="33b39-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="33b39-113">解説</span><span class="sxs-lookup"><span data-stu-id="33b39-113">Remarks</span></span>

<span data-ttu-id="33b39-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="33b39-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```