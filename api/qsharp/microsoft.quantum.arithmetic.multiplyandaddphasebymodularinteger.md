---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223869"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="efdf2-102">MultiplyAndAddPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="efdf2-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="efdf2-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="efdf2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="efdf2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efdf2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efdf2-105">MultiplyAndAddByModularInteger と同じですが、summand が QFT ベースで整数をエンコードすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="efdf2-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="efdf2-106">入力</span><span class="sxs-lookup"><span data-stu-id="efdf2-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="efdf2-107">[型の型: Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="efdf2-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="efdf2-108">各 basis 状態ラベルに追加する整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="efdf2-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="efdf2-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="efdf2-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="efdf2-110">に関して、加算と乗算が行われる剰余 $N $。</span><span class="sxs-lookup"><span data-stu-id="efdf2-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="efdf2-111">乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="efdf2-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="efdf2-112">の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。</span><span class="sxs-lookup"><span data-stu-id="efdf2-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="efdf2-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="efdf2-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="efdf2-114">この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="efdf2-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="efdf2-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="efdf2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="efdf2-116">解説</span><span class="sxs-lookup"><span data-stu-id="efdf2-116">Remarks</span></span>

<span data-ttu-id="efdf2-117">は `phaseSummand` 、の最上位ビットが0に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="efdf2-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="efdf2-118">また、の値が $N $ 未満であることを前提としてい `phaseSummand` ます。</span><span class="sxs-lookup"><span data-stu-id="efdf2-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="efdf2-119">参照</span><span class="sxs-lookup"><span data-stu-id="efdf2-119">See Also</span></span>

- [<span data-ttu-id="efdf2-120">MultiplyAndAddByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="efdf2-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)