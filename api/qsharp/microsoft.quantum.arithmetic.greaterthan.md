---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846633"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="aa1e8-102">GreaterThan 操作</span><span class="sxs-lookup"><span data-stu-id="aa1e8-102">GreaterThan operation</span></span>

<span data-ttu-id="aa1e8-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa1e8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa1e8-105">Qubit レジスタにエンコードされた2つの整数の間で、比較の結果に基づいてターゲットの qubit を反転させることにより、より大きい比較を適用します。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="aa1e8-106">説明</span><span class="sxs-lookup"><span data-stu-id="aa1e8-106">Description</span></span>

<span data-ttu-id="aa1e8-107">は、qubit レジスタ xs および y でエンコードされた、$ および $y $ $x 2 つの整数の比較を厳密に上回る比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="aa1e8-108">$X > y $ の場合は、結果の qubit が反転されます。それ以外の場合、結果の qubit はその状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="aa1e8-109">入力</span><span class="sxs-lookup"><span data-stu-id="aa1e8-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="aa1e8-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa1e8-111">LittleEndian qubit レジスタは、$ $x 最初の整数をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="aa1e8-112">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa1e8-113">LittleEndian qubit レジスタでは、2番目の整数 $y $ としてエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="aa1e8-114">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa1e8-115">Y $ $x > 場合に反転される単一の qubit。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa1e8-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa1e8-117">解説</span><span class="sxs-lookup"><span data-stu-id="aa1e8-117">Remarks</span></span>

<span data-ttu-id="aa1e8-118">は、-y = (x ' + y) ' $ の $x を使用します。ここで、' は1の補数を表します。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="aa1e8-119">References</span><span class="sxs-lookup"><span data-stu-id="aa1e8-119">References</span></span>

- <span data-ttu-id="aa1e8-120">Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。</span><span class="sxs-lookup"><span data-stu-id="aa1e8-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="aa1e8-121">トーマス Haener、Martin Roetteler、Krysta: "2n + 2 qubits と Toffoli ベースのモジュール乗算を使用したファクタリング"、2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="aa1e8-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>