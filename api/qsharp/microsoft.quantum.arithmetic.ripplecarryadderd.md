---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: b87c8f25acc8854d5e8d28f58cfc99dffb92a973
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222118"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="0aaca-102">RippleCarryAdderD 操作</span><span class="sxs-lookup"><span data-stu-id="0aaca-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="0aaca-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0aaca-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0aaca-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0aaca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0aaca-105">元に戻すことができ、2つの整数がインプレース適用されます。</span><span class="sxs-lookup"><span data-stu-id="0aaca-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="0aaca-106">LittleEndian レジスタにエンコードされた2つの $n $ ビット整数 `xs` `ys` と、qubit が渡された場合、演算は2つの整数の合計を計算します。この2つの整数は、結果の最下位の $n $ が保持され、 `ys` 実行ビットは qubit に xor され `carry` ます。</span><span class="sxs-lookup"><span data-stu-id="0aaca-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0aaca-107">入力</span><span class="sxs-lookup"><span data-stu-id="0aaca-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0aaca-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0aaca-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0aaca-109">LittleEndian qubit レジスタは、最初の整数 summand をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0aaca-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0aaca-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0aaca-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0aaca-111">LittleEndian qubit レジスタエンコーディング2番目の整数 summand は、合計の最下位のビット $n を保持するように変更されています。</span><span class="sxs-lookup"><span data-stu-id="0aaca-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0aaca-112">キャリー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0aaca-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0aaca-113">キャリー qubit, は、合計の最上位ビットを xor しています。</span><span class="sxs-lookup"><span data-stu-id="0aaca-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0aaca-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0aaca-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0aaca-115">解説</span><span class="sxs-lookup"><span data-stu-id="0aaca-115">Remarks</span></span>

<span data-ttu-id="0aaca-116">指定された制御操作は、操作の対称および相互キャンセルを利用して、すべての操作にコントロールを追加する既定の実装を改善します。</span><span class="sxs-lookup"><span data-stu-id="0aaca-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0aaca-117">リファレンス</span><span class="sxs-lookup"><span data-stu-id="0aaca-117">References</span></span>

- <span data-ttu-id="0aaca-118">Draper: "Quantum コンピューターでの追加"、2000。</span><span class="sxs-lookup"><span data-stu-id="0aaca-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033