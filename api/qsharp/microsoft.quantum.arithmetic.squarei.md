---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221863"
---
# <a name="squarei-operation"></a><span data-ttu-id="9e2e0-102">SquareI 操作</span><span class="sxs-lookup"><span data-stu-id="9e2e0-102">SquareI operation</span></span>

<span data-ttu-id="9e2e0-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9e2e0-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9e2e0-105">整数の2乗をに計算し `xs` `result` ます。最初はゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e2e0-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9e2e0-106">入力</span><span class="sxs-lookup"><span data-stu-id="9e2e0-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9e2e0-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9e2e0-108">$n $ ビットの数値を平方根 (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="9e2e0-109">結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9e2e0-110">$ 2n $ ビット結果 (LittleEndian) は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="9e2e0-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e2e0-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e2e0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9e2e0-112">解説</span><span class="sxs-lookup"><span data-stu-id="9e2e0-112">Remarks</span></span>

<span data-ttu-id="9e2e0-113">は、標準的なシフトアンド追加アプローチを使用して、正方形を計算します。</span><span class="sxs-lookup"><span data-stu-id="9e2e0-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="9e2e0-114">は、通常の乗数を適用してコピー操作を元に戻す前に、最初に xs をコピーする、ストレート転送ソリューションと比較して $n-$1 qubits を保存します。</span><span class="sxs-lookup"><span data-stu-id="9e2e0-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>