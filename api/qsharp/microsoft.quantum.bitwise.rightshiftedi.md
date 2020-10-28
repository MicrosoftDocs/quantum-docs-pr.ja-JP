---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718579"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="43b0a-102">RightShiftedI 関数</span><span class="sxs-lookup"><span data-stu-id="43b0a-102">RightShiftedI function</span></span>

<span data-ttu-id="43b0a-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="43b0a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="43b0a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43b0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43b0a-105">数値のビットごとの表現を指定されたビット数だけ右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="43b0a-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="43b0a-106">入力</span><span class="sxs-lookup"><span data-stu-id="43b0a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="43b0a-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43b0a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43b0a-108">ビットごとの表現を右にシフトする数値 (重要ではない)。</span><span class="sxs-lookup"><span data-stu-id="43b0a-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="43b0a-109">amount: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43b0a-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43b0a-110">を右にシフトするときに使用するビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="43b0a-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="43b0a-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43b0a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43b0a-112">ビットで右にシフトされたの値 `value` `amount` 。</span><span class="sxs-lookup"><span data-stu-id="43b0a-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="43b0a-113">解説</span><span class="sxs-lookup"><span data-stu-id="43b0a-113">Remarks</span></span>

<span data-ttu-id="43b0a-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43b0a-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```