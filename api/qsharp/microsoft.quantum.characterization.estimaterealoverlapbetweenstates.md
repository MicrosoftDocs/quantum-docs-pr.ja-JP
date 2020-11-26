---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: d9f569ceffc16f377189dc94035213b9075609cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216185"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>EstimateRealOverlapBetweenStates 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


それぞれの状態のコピーを準備する2つの操作を実行すると、各操作によって準備された状態間の重複部分が推定されます。

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>入力

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞

固定の入力状態を準備する操作。


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

比較する2つの状態準備操作の最初の。


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

比較する2つの状態準備操作の2番目の。


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

、、および all が動作する qubits の数 `commonPreparation` `preparation1` `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

重複の推定に使用する測定値の数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>解説

この操作では、Hadamard テストを使用して、$ $ \begin{align} \braket{\psi | の実数部を検索します。V ^ {\ dagger} U |\psi} \end{align} $ $ ここで、$ \ket{\psi} $ はによって準備された状態であり `commonPreparation` $U、$ はのアクションのユニタリ表現で `preparation1` あり、$V $ はに対応し `preparation2` ます。

## <a name="references"></a>リファレンス

- Aharonov *et al.* [/0511096 のように](https://arxiv.org/abs/quant-ph/0511096)なります。

## <a name="see-also"></a>参照

- [EstimateImagOverlapBetweenStates (Microsoft... 特性)](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [EstimateOverlapBetweenStates (Microsoft... 特性)](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)