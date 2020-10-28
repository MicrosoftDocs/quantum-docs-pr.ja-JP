---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713680"
---
# <a name="measurementoperators-function"></a>MeasurementOperators 関数

名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

パック [](https://nuget.org/packages/)


Jordan-Wigner 用語の予測を計算するために必要なすべての測定演算子を計算します。

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

分子システムをシミュレートするために必要な qubits の数。


### <a name="indices--int"></a>インデックス: [Int](xref:microsoft.quantum.lang-ref.int)[]

各 P# li 演算子が適用される qubit のインデックスを格納している配列。


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner 用語の型。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []

測定演算子の配列 (それぞれが Pan Li の配列)。