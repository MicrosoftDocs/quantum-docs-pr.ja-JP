---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719803"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="b236b-102">MultiplyAndAddPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="b236b-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="b236b-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b236b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b236b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b236b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b236b-105">MultiplyAndAddByModularInteger と同じですが、summand が QFT ベースで整数をエンコードすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b236b-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b236b-106">入力</span><span class="sxs-lookup"><span data-stu-id="b236b-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="b236b-107">[型の型: Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b236b-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b236b-108">各 basis 状態ラベルに追加する整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="b236b-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="b236b-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b236b-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b236b-110">に関して、加算と乗算が行われる剰余 $N $。</span><span class="sxs-lookup"><span data-stu-id="b236b-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="b236b-111">乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b236b-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b236b-112">の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。</span><span class="sxs-lookup"><span data-stu-id="b236b-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="b236b-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b236b-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b236b-114">この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="b236b-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b236b-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b236b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b236b-116">解説</span><span class="sxs-lookup"><span data-stu-id="b236b-116">Remarks</span></span>

<span data-ttu-id="b236b-117">は `phaseSummand` 、の最上位ビットが0に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b236b-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="b236b-118">また、の値が $N $ 未満であることを前提としてい `phaseSummand` ます。</span><span class="sxs-lookup"><span data-stu-id="b236b-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b236b-119">参照</span><span class="sxs-lookup"><span data-stu-id="b236b-119">See Also</span></span>

- [<span data-ttu-id="b236b-120">MultiplyAndAddByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="b236b-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)