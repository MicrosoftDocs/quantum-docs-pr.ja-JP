---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: P# liarrayasint 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713372"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="01f7d-102">P# liarrayasint 関数</span><span class="sxs-lookup"><span data-stu-id="01f7d-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="01f7d-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="01f7d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="01f7d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01f7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01f7d-105">シングル qubit の演算子の配列として表されるマルチ qubit の Pan Li 演算子を整数にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="01f7d-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="01f7d-106">入力</span><span class="sxs-lookup"><span data-stu-id="01f7d-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="01f7d-107">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="01f7d-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="01f7d-108">最大31のシングル qubit の演算子の配列。</span><span class="sxs-lookup"><span data-stu-id="01f7d-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="01f7d-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01f7d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01f7d-110">`paulis`次に示すように、一意に識別する整数。</span><span class="sxs-lookup"><span data-stu-id="01f7d-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="01f7d-111">解説</span><span class="sxs-lookup"><span data-stu-id="01f7d-111">Remarks</span></span>

<span data-ttu-id="01f7d-112">各 P\begin{align} Li 演算子は、次の2つのビットを使用してエンコードすることができます: $ $ \ bold 完了 \ mapに 00,、\ quad X-mapに 01,、\ quad Y-マップ</span><span class="sxs-lookup"><span data-stu-id="01f7d-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="01f7d-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="01f7d-113">\end{align} $$</span></span>

<span data-ttu-id="01f7d-114">これらの演算子の配列を指定した `[P0, ..., Pn]` 場合、この関数は、ビッグエンディアン順で各 Pan li 演算子のマッピングを連結することによって、バイナリ拡張を含む整数を返し `bits(Pn) ... bits(P0)` ます。</span><span class="sxs-lookup"><span data-stu-id="01f7d-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>