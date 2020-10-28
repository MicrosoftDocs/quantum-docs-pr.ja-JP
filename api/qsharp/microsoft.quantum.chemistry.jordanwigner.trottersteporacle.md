---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: TrotterStepOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713769"
---
# <a name="trottersteporacle-function"></a>TrotterStepOracle 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


Trotter step 操作と、それを実行するために必要なパラメーターを返します。

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>入力

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

形式で記述された Hamiltonian `JordanWignerEncodingData` 。


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Trotter インテグレーターのステップサイズ。


### <a name="trotterorder--int"></a>trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)

Trotter インテグレーターの順序。



## <a name="output--intdoublequbit--unit-adj--ctl"></a>出力: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl))

タプル。ここで、は `Int` 割り当てられた qubits の数、 `Double` は `1.0/trotterStepSize` で、操作は Trotter ステップです。