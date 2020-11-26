---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209861"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="0f17c-102">LeftShiftedI 関数</span><span class="sxs-lookup"><span data-stu-id="0f17c-102">LeftShiftedI function</span></span>

<span data-ttu-id="0f17c-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="0f17c-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="0f17c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f17c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f17c-105">指定されたビット数だけ左にある数値のビットごとの表現をシフトします。</span><span class="sxs-lookup"><span data-stu-id="0f17c-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="0f17c-106">入力</span><span class="sxs-lookup"><span data-stu-id="0f17c-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="0f17c-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f17c-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f17c-108">ビットごとの表現を左にシフトする数値 (より大きい)。</span><span class="sxs-lookup"><span data-stu-id="0f17c-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="0f17c-109">amount: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f17c-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f17c-110">を左にシフトするときに使用するビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="0f17c-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="0f17c-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f17c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f17c-112">ビットで左にシフトされたの値 `value` `amount` 。</span><span class="sxs-lookup"><span data-stu-id="0f17c-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f17c-113">解説</span><span class="sxs-lookup"><span data-stu-id="0f17c-113">Remarks</span></span>

<span data-ttu-id="0f17c-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f17c-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```