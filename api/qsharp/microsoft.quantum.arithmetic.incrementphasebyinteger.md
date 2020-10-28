---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721075"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="46fc3-102">IncrementPhaseByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="46fc3-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="46fc3-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="46fc3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="46fc3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46fc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46fc3-105">フェーズ回転を使用して、古典的な整数によって署名されていないクォンタムレジスタをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="46fc3-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="46fc3-106">説明</span><span class="sxs-lookup"><span data-stu-id="46fc3-106">Description</span></span>

<span data-ttu-id="46fc3-107">は、 `target` リトルエンディアンエンコーディングで $ $x $ の符号なし整数をエンコードし、 `increment` $a $ と等しいとします。</span><span class="sxs-lookup"><span data-stu-id="46fc3-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="46fc3-108">次に、この操作では、ユニタリ $ \ket{x} \ map\ket{x + a} $ を実装します。この場合、加算は $ 2 ^ n $ という剰余が実行されます。ここで、$n = \texttt{Length (target!)}$.</span><span class="sxs-lookup"><span data-stu-id="46fc3-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="46fc3-109">入力</span><span class="sxs-lookup"><span data-stu-id="46fc3-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="46fc3-110">increment: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46fc3-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46fc3-111">のインクリメントに使用する整数 `target` 。</span><span class="sxs-lookup"><span data-stu-id="46fc3-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="46fc3-112">ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="46fc3-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="46fc3-113">デュアルエンディアンエンコーディング (QFT) を使用して、符号なし整数をエンコードするクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="46fc3-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46fc3-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46fc3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="46fc3-115">解説</span><span class="sxs-lookup"><span data-stu-id="46fc3-115">Remarks</span></span>

<span data-ttu-id="46fc3-116">回線は単純化されています。これは、増分が、クォンタムレジスタではなく、古典的な定数であるためです。</span><span class="sxs-lookup"><span data-stu-id="46fc3-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="46fc3-117">サーキットの図と説明については、 [ arXiv のページ6の図である quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46fc3-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="46fc3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="46fc3-118">References</span></span>

- [<span data-ttu-id="46fc3-119">*Draper* , arxiv: quant-ph/0008033</span><span class="sxs-lookup"><span data-stu-id="46fc3-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="46fc3-120">参照</span><span class="sxs-lookup"><span data-stu-id="46fc3-120">See Also</span></span>

- [<span data-ttu-id="46fc3-121">IncrementByInteger です。</span><span class="sxs-lookup"><span data-stu-id="46fc3-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)