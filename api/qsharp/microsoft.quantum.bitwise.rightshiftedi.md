---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845252"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="1451b-102">RightShiftedI 関数</span><span class="sxs-lookup"><span data-stu-id="1451b-102">RightShiftedI function</span></span>

<span data-ttu-id="1451b-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="1451b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1451b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1451b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1451b-105">数値のビットごとの表現を指定されたビット数だけ右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="1451b-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="1451b-106">入力</span><span class="sxs-lookup"><span data-stu-id="1451b-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="1451b-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1451b-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1451b-108">ビットごとの表現を右にシフトする数値 (重要ではない)。</span><span class="sxs-lookup"><span data-stu-id="1451b-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="1451b-109">amount: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1451b-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1451b-110">を右にシフトするときに使用するビット数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="1451b-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="1451b-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1451b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1451b-112">ビットで右にシフトされたの値 `value` `amount` 。</span><span class="sxs-lookup"><span data-stu-id="1451b-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="1451b-113">解説</span><span class="sxs-lookup"><span data-stu-id="1451b-113">Remarks</span></span>

<span data-ttu-id="1451b-114">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1451b-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```