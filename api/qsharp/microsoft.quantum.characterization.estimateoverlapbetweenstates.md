---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839712"
---
# <a name="estimateoverlapbetweenstates-operation"></a>EstimateOverlapBetweenStates 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


それぞれの状態のコピーを準備する2つの操作を実行すると、各操作によって準備された状態間の2乗された重複が推定されます。

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>入力

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

比較する2つの状態準備操作の最初の。


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

比較する2つの状態準備操作の2番目の。


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

、、および all が動作する qubits の数 `commonPreparation` `preparation1` `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

重複の推定に使用する測定値の数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>解説

この操作では、スワップテストを使用して $ $ \begin{align}/left | を検索します。\braket{00\cdots 0 |V ^ {\ dagger} U |00 \ cdots 0} \ 右 | ^ 2 \end{align} $ $ ここで $U $ は、のアクションのユニタリ表現で、 `preparation1` $V $ はに対応し `preparation2` ます。

## <a name="see-also"></a>参照

- [EstimateRealOverlapBetweenStates (Microsoft... 特性)](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [EstimateImagOverlapBetweenStates (Microsoft... 特性)](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)