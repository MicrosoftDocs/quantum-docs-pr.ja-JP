---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835664"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation 操作

名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


指定された Jordan-Wigner Hamiltonian term に関連するエネルギーを計算します

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>説明

この操作では、各測定演算子に関連付けられた予測値を推定し、サンプリングを使用して対応する係数で乗算します。
結果は、Jordan-Wigner 用語のエネルギーを含む変数に集計されます。

## <a name="input"></a>入力

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

状態の準備に使用されるユニタリ。


### <a name="ops--pauli"></a>ops: [Pの li](xref:microsoft.quantum.lang-ref.pauli)[] []

Jordan-Wigner 用語の測定演算子。


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner 用語の係数。


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

分子システムをシミュレートするために必要な qubits の数。


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

想定用語の推定に使用するサンプル数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

Jordan-Wigner 用語に関連付けられているエネルギー。