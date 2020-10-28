---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721274"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="2cc6c-102">CompareUsingRippleCarry 操作</span><span class="sxs-lookup"><span data-stu-id="2cc6c-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="2cc6c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2cc6c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2cc6c-105">この操作では、qubits のレジスタによって表される整数がもう1つの整数より大きいかどうかをテストして、結果の XOR を出力 qubits に適用します。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="2cc6c-106">説明</span><span class="sxs-lookup"><span data-stu-id="2cc6c-106">Description</span></span>

<span data-ttu-id="2cc6c-107">2つの整数が指定され、 `x` `y` 同じサイズの qubit レジスタに格納されている場合、この操作は、が満たされているかどうかを確認し `x > y` ます。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="2cc6c-108">True の場合、1は出力 qubit に Xor ます。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="2cc6c-109">それ以外の場合、0は出力 qubit に Xor されます。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="2cc6c-110">言い換えると、この操作は、ユニタリ $ $ \begin{align} U\ket {x} \ k {y} \ k {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} で表すことができます。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="2cc6c-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2cc6c-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="2cc6c-112">入力</span><span class="sxs-lookup"><span data-stu-id="2cc6c-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="2cc6c-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2cc6c-114">Qubit レジスタの形式で格納されている、比較対象の最初の数値 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="2cc6c-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2cc6c-116">Qubit レジスタの形式で格納されている比較対象の2番目の数値 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="2cc6c-117">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2cc6c-118">比較 $x>y $ の結果を格納する qubit。</span><span class="sxs-lookup"><span data-stu-id="2cc6c-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cc6c-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cc6c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2cc6c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cc6c-120">References</span></span>

- <span data-ttu-id="2cc6c-121">新しいクォンタム ripple、Cuccaro、Draper、Samuel、Kutin、David Petrie を追加していますので、 https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="2cc6c-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>