---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: QubitizationOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: 326bebfc1cfd839082732898167c20ecf105a266
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713811"
---
# <a name="qubitizationoracle-function"></a>QubitizationOracle 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


Qubitization 操作と、それを実行するために必要なパラメーターを返します。

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>入力

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

形式で記述された Hamiltonian `JordanWignerEncodingData` 。



## <a name="output--intdoublequbit--unit-adj--ctl"></a>出力: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl))

タプル。ここで、は、 `Int` 割り当てられた qubits の数、 `Double` は Hamiltonian 係数の1基準であり、操作は Qubitization によって作成されたクォンタムウォークです。