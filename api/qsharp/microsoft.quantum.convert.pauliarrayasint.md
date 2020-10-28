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
# <a name="pauliarrayasint-function"></a>P# liarrayasint 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


シングル qubit の演算子の配列として表されるマルチ qubit の Pan Li 演算子を整数にエンコードします。

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

最大31のシングル qubit の演算子の配列。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

`paulis`次に示すように、一意に識別する整数。

## <a name="remarks"></a>解説

各 P\begin{align} Li 演算子は、次の2つのビットを使用してエンコードすることができます: $ $ \ bold 完了 \ mapに 00,、\ quad X-mapに 01,、\ quad Y-マップ
\end{align} $ $

これらの演算子の配列を指定した `[P0, ..., Pn]` 場合、この関数は、ビッグエンディアン順で各 Pan li 演算子のマッピングを連結することによって、バイナリ拡張を含む整数を返し `bits(Pn) ... bits(P0)` ます。