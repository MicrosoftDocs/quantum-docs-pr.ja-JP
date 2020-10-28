---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718531"
---
# <a name="zbits-function"></a><span data-ttu-id="09c39-102">ZBits 関数</span><span class="sxs-lookup"><span data-stu-id="09c39-102">ZBits function</span></span>

<span data-ttu-id="09c39-103">名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理</span><span class="sxs-lookup"><span data-stu-id="09c39-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="09c39-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09c39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09c39-105">P# li 演算子の配列の Z ビットを表す整数を返します。</span><span class="sxs-lookup"><span data-stu-id="09c39-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="09c39-106">入力</span><span class="sxs-lookup"><span data-stu-id="09c39-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="09c39-107">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="09c39-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="09c39-108">整数として表現される、P# li 演算子の配列。</span><span class="sxs-lookup"><span data-stu-id="09c39-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="09c39-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09c39-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09c39-110">$ をバイナリ表現 $ (p_ {62} \, p_ {61} \, \ ドット p_0) $ に $x 整数を指定 \, `paulis[i]` `PauliI` `PauliX` し `paulis[i]` `PauliY` `PauliZ` ます。がまたはの場合は $p _i = $0、がまたはの場合は $p _i = $1 になります。</span><span class="sxs-lookup"><span data-stu-id="09c39-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="09c39-111">解説</span><span class="sxs-lookup"><span data-stu-id="09c39-111">Remarks</span></span>

<span data-ttu-id="09c39-112">配列の長さが63より大きい場合、関数はをスローし `paulis` ます。</span><span class="sxs-lookup"><span data-stu-id="09c39-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="09c39-113">参照</span><span class="sxs-lookup"><span data-stu-id="09c39-113">See Also</span></span>

- [<span data-ttu-id="09c39-114">Microsoft...... x ビット</span><span class="sxs-lookup"><span data-stu-id="09c39-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)