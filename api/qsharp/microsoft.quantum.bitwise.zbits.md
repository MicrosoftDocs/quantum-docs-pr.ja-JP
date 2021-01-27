---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842057"
---
# <a name="zbits-function"></a><span data-ttu-id="b1ef7-102">ZBits 関数</span><span class="sxs-lookup"><span data-stu-id="b1ef7-102">ZBits function</span></span>

<span data-ttu-id="b1ef7-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="b1ef7-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="b1ef7-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="b1ef7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b1ef7-105">P# li 演算子の配列の Z ビットを表す整数を返します。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="b1ef7-106">入力</span><span class="sxs-lookup"><span data-stu-id="b1ef7-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="b1ef7-107">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b1ef7-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b1ef7-108">整数として表現される、P# li 演算子の配列。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="b1ef7-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1ef7-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1ef7-110">$ をバイナリ表現 $ (p_ {62} \, p_ {61} \, \ ドット p_0) $ に $x 整数を指定 \, `paulis[i]` `PauliI` `PauliX` し `paulis[i]` `PauliY` `PauliZ` ます。がまたはの場合は $p _i = $0、がまたはの場合は $p _i = $1 になります。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1ef7-111">解説</span><span class="sxs-lookup"><span data-stu-id="b1ef7-111">Remarks</span></span>

<span data-ttu-id="b1ef7-112">配列の長さが63より大きい場合、関数はをスローし `paulis` ます。</span><span class="sxs-lookup"><span data-stu-id="b1ef7-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1ef7-113">参照</span><span class="sxs-lookup"><span data-stu-id="b1ef7-113">See Also</span></span>

- [<span data-ttu-id="b1ef7-114">Microsoft...... x ビット</span><span class="sxs-lookup"><span data-stu-id="b1ef7-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)