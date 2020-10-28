---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718574"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="bede6-102">RightShiftedL 関数</span><span class="sxs-lookup"><span data-stu-id="bede6-102">RightShiftedL function</span></span>

<span data-ttu-id="bede6-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="bede6-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bede6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bede6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bede6-105">数値のビットごとの表現を指定されたビット数だけ右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="bede6-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="bede6-106">入力</span><span class="sxs-lookup"><span data-stu-id="bede6-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="bede6-107">値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bede6-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bede6-108">ビットごとの表現を右にシフトする数値 (重要ではない)。</span><span class="sxs-lookup"><span data-stu-id="bede6-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="bede6-109">amount: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bede6-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bede6-110">を右にシフトするときに使用するビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="bede6-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="bede6-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bede6-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bede6-112">ビットで右にシフトされたの値 `value` `amount` 。</span><span class="sxs-lookup"><span data-stu-id="bede6-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="bede6-113">解説</span><span class="sxs-lookup"><span data-stu-id="bede6-113">Remarks</span></span>

<span data-ttu-id="bede6-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bede6-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```