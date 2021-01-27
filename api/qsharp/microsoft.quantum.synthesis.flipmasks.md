---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859203"
---
# <a name="flipmasks-function"></a>FlipMasks 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2レベルのすべての列では、"フリップマスク" を計算します。これは、対応する 1-qubits ゲートを適用する前と後の逆にする必要がある qubits を表します。
便宜上、便宜のために0を使用します。

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>入力

### <a name="decomposition--complexintint"></a>分解: ([Complex](xref:Microsoft.Quantum.Math.Complex)[] []、[int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="allqubitsmask--int"></a>allQubitsMask: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

