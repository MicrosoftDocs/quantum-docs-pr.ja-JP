---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846515"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="9a663-102">MultiplyAndAddByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="9a663-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="9a663-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9a663-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9a663-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a663-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a663-105">Qubit レジスタに対して、モジュールの乗算および加算による整数定数を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a663-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9a663-106">説明</span><span class="sxs-lookup"><span data-stu-id="9a663-106">Description</span></span>

<span data-ttu-id="9a663-107">指定された剰余 $N $、定数乗数 $a $、および \ket{$y $ に対して、map $ $ \begin{align} \ket{x} \ket{b}/map\end{align} $ $ summand (b + a/cdot x) $ $ を実装します。</span><span class="sxs-lookup"><span data-stu-id="9a663-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="9a663-108">入力</span><span class="sxs-lookup"><span data-stu-id="9a663-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="9a663-109">[型の型: Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a663-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a663-110">各 basis 状態ラベルに追加する整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="9a663-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="9a663-111">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a663-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a663-112">に関して、加算と乗算が行われる剰余 $N $。</span><span class="sxs-lookup"><span data-stu-id="9a663-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="9a663-113">乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9a663-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9a663-114">の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。</span><span class="sxs-lookup"><span data-stu-id="9a663-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="9a663-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9a663-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9a663-116">この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="9a663-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a663-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a663-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9a663-118">解説</span><span class="sxs-lookup"><span data-stu-id="9a663-118">Remarks</span></span>

- <span data-ttu-id="9a663-119">回路図と説明については、arXiv のページ7の図6を参照してください [: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="9a663-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="9a663-120">この操作は[Arxiv: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)の CMULT (a) MOD (N) に対応します。</span><span class="sxs-lookup"><span data-stu-id="9a663-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="9a663-121">参照</span><span class="sxs-lookup"><span data-stu-id="9a663-121">See Also</span></span>

- [<span data-ttu-id="9a663-122">MultiplyAndAddPhaseByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="9a663-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)