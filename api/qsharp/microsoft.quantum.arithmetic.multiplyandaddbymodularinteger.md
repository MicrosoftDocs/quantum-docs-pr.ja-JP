---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719810"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="95c3f-102">MultiplyAndAddByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="95c3f-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="95c3f-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="95c3f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="95c3f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95c3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95c3f-105">Qubit レジスタに対して、モジュールの乗算および加算による整数定数を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3f-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="95c3f-106">説明</span><span class="sxs-lookup"><span data-stu-id="95c3f-106">Description</span></span>

<span data-ttu-id="95c3f-107">指定された剰余 $N $、定数乗数 $a $、および \ket{$y $ に対して、map $ $ \begin{align} \ket{x} \ket{b}/map\end{align} $ $ summand (b + a/cdot x) $ $ を実装します。</span><span class="sxs-lookup"><span data-stu-id="95c3f-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="95c3f-108">入力</span><span class="sxs-lookup"><span data-stu-id="95c3f-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="95c3f-109">[型の型: Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95c3f-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95c3f-110">各 basis 状態ラベルに追加する整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="95c3f-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="95c3f-111">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95c3f-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95c3f-112">に関して、加算と乗算が行われる剰余 $N $。</span><span class="sxs-lookup"><span data-stu-id="95c3f-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="95c3f-113">乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="95c3f-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="95c3f-114">の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。</span><span class="sxs-lookup"><span data-stu-id="95c3f-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="95c3f-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="95c3f-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="95c3f-116">この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="95c3f-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95c3f-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95c3f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="95c3f-118">解説</span><span class="sxs-lookup"><span data-stu-id="95c3f-118">Remarks</span></span>

- <span data-ttu-id="95c3f-119">回路図と説明については、arXiv のページ7の図6を参照してください [: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="95c3f-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="95c3f-120">この操作は[Arxiv: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)の CMULT (a) MOD (N) に対応します。</span><span class="sxs-lookup"><span data-stu-id="95c3f-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="95c3f-121">参照</span><span class="sxs-lookup"><span data-stu-id="95c3f-121">See Also</span></span>

- [<span data-ttu-id="95c3f-122">MultiplyAndAddPhaseByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="95c3f-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)