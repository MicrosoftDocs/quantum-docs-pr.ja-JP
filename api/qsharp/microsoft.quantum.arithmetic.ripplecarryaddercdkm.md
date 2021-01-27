---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846358"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="a7eda-102">RippleCarryAdderCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="a7eda-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="a7eda-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a7eda-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a7eda-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7eda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7eda-105">元に戻すことができ、2つの整数がインプレース適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7eda-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a7eda-106">説明</span><span class="sxs-lookup"><span data-stu-id="a7eda-106">Description</span></span>

<span data-ttu-id="a7eda-107">LittleEndian レジスタにエンコードされた2つの $n $ ビット整数 `xs` `ys` と、qubit が渡された場合、演算は2つの整数の合計を計算します。この2つの整数は、結果の最下位の $n $ が保持され、 `ys` 実行ビットは qubit に xor され `carry` ます。</span><span class="sxs-lookup"><span data-stu-id="a7eda-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="a7eda-108">入力</span><span class="sxs-lookup"><span data-stu-id="a7eda-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a7eda-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a7eda-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a7eda-110">LittleEndian qubit レジスタは、最初の整数 summand をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="a7eda-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a7eda-111">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a7eda-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a7eda-112">2番目の整数 summand を LittleEndian qubit レジスタにエンコードすると、その合計の最下位ビットを保持するように変更されます。</span><span class="sxs-lookup"><span data-stu-id="a7eda-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="a7eda-113">キャリー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a7eda-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a7eda-114">キャリー qubit, は、合計の最上位ビットを xor しています。</span><span class="sxs-lookup"><span data-stu-id="a7eda-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7eda-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7eda-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a7eda-116">解説</span><span class="sxs-lookup"><span data-stu-id="a7eda-116">Remarks</span></span>

<span data-ttu-id="a7eda-117">この操作には、RippleCarryAdderD と同じ機能がありますが、$n $ ではなく、補助 qubit を1つだけ使用します。</span><span class="sxs-lookup"><span data-stu-id="a7eda-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="a7eda-118">References</span><span class="sxs-lookup"><span data-stu-id="a7eda-118">References</span></span>

- <span data-ttu-id="a7eda-119">Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。</span><span class="sxs-lookup"><span data-stu-id="a7eda-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1