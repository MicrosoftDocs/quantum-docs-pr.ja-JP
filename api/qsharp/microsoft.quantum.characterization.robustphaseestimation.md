---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851800"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された oracle および eigenstate に対して、反復的ではない堅牢なクォンタムフェーズの推定アルゴリズムを実行 `U` し、ハイゼンベルグ limit での差異のスケーリングにより、フェーズの1つの実際の値の見積もりを提供します。

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>入力

### <a name="bitsprecision--int"></a>bitsPrecision: [Int](xref:microsoft.quantum.lang-ref.int)

これにより、$-シグマ/le 10.7 \ pi/\ text{# of queries} $ のような多数のクエリを使用して、標準偏差 $/シグマ/le 2 \ pi/2 ^ \text{bitsPrecision} $ の推定値が $/phi $ になります。


### <a name="oracle--discreteoracle"></a>oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

指定された整数に $U ^ m $ を実装する操作では $m $ が使用されます。


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ Act を $U するクォンタムレジスタ。 Eigenstate $ \ket{\phi} $ of $U $ が格納されている場合は $U、$ \phi\in (-\ pi,-pi) $ の \ket{\phi} = e ^ {i} \ket{\phi} $ が不明なフェーズになります。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>解説

クエリ数が多い場合、$/phi $ を満たす $/phi $ に対する標準偏差の下限を Cramer-Rao します (クエリの数は $/シグマ)。この値を超えると、クエリは {# of queries} $ となります。

## <a name="references"></a>References

- 堅牢なフェーズ推定 Shelby Kimmel、Guang Hao Low、Theodore J 氏によるユニバーサル Single-Qubit Gate-Set の堅牢な調整 https://arxiv.org/abs/1502.02677