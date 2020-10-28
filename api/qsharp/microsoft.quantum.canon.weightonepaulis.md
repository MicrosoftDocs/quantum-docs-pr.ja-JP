---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715197"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された数の qubits に対するすべての重み-1 の Pan Li 演算子の配列を返します。

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

返された P# li 演算子が定義されている qubits の数。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []

マルチビット演算子の配列。それぞれが長さの配列として表され `nQubits` ます。