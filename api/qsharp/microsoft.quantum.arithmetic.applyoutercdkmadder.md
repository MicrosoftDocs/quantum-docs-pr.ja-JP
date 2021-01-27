---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843718"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="fc675-102">ApplyOuterCDKMAdder 操作</span><span class="sxs-lookup"><span data-stu-id="fc675-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="fc675-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fc675-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fc675-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc675-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc675-105">次の整数加算演算 RippleCarryAdderCDKM で使用される、元に戻すことができるインプレース操作。</span><span class="sxs-lookup"><span data-stu-id="fc675-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="fc675-106">2つの qubit レジスタと同じ長さが指定されて `xs` `ys` いる場合、この操作は、内の qubit と、 `xs` `ys` ターゲットとしてのコントロールおよび qubit を使用して、リップ not と ccnot ゲートの ripple キャリーシーケンスを適用し `xs` ます。</span><span class="sxs-lookup"><span data-stu-id="fc675-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fc675-107">入力</span><span class="sxs-lookup"><span data-stu-id="fc675-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="fc675-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc675-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fc675-109">コントロールとターゲットを含む最初の qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="fc675-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="fc675-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc675-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fc675-111">2番目の qubit レジスタ。コントロールに貢献します。</span><span class="sxs-lookup"><span data-stu-id="fc675-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="fc675-112">ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fc675-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fc675-113">この操作に渡された RippleCarryAdderCDKM で使用される ancilla qubit。</span><span class="sxs-lookup"><span data-stu-id="fc675-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc675-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc675-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="fc675-115">References</span><span class="sxs-lookup"><span data-stu-id="fc675-115">References</span></span>

- <span data-ttu-id="fc675-116">Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。</span><span class="sxs-lookup"><span data-stu-id="fc675-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1