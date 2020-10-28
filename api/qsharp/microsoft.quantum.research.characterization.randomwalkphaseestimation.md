---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710880"
---
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation 操作

名前空間: [Microsoft. Quantum. 特性](xref:Microsoft.Quantum.Research.Characterization)

パック [](https://nuget.org/packages/)


指定された oracle および eigenstate からの古典的な測定結果に対するベイジアン推定を概算するランダムウォークを使用して反復フェーズ推定を実行します。

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>入力

### <a name="initialmean--double"></a>initialMean: [Double](xref:microsoft.quantum.lang-ref.double)

最初の標準正規分布の平均値 $-phi $。


### <a name="initialstddev--double"></a>initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)

初期正規分布の標準偏差 ($/phi $ 経由)。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

最終的な事後見積もらに許容される測定値の数。


### <a name="maxmeasurements--int"></a>maxMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

操作が失敗したと見なされるまでに取得できる測定の合計数。


### <a name="unwind--int"></a>アンワインド: [Int](xref:microsoft.quantum.lang-ref.int)

整合性チェックが失敗した場合に破棄する結果の数。


### <a name="oracle--continuousoracle"></a>oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

$U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ (不明なフェーズ $ \ phi \、\mathbb{R} ^ + $) を含む、型の $U $ を表す演算。


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ Act $U れるレジスタ。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

最終的な推定 $ \hat{\phi} \mathrel{: =} \ [-phi] $ が期待される場合は、事後によって受け入れられるすべてのデータが返されます。

## <a name="remarks"></a>解説

### <a name="iterative-phase-estimation-and-eigenstates"></a>反復フェーズの推定と Eigenstates

一般に、入力レジスタは `eigenstate` $U $ の eigenstate $ \ket{\phi} $ である必要はありませんが、eigenstate の法則にすることができます。 入力状態が指定されていることを想定しています。 \begin{align} \ket{\psi} & = \ sum \_ {j}-alpha \_ j \ket{\phi \_ j}, \end{align}、$- \{ alpha j \_ \} $ は複雑な係数で、$ \ sum \_ j | \ alpha \_ j | ^ 2 = $1、where $U \ket{\phi \_ j} = \ phi \_ j\ket {\ phi \_ j} $。

次に、 [開発ガイド](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)で説明されているように、反復フェーズの推定を実行すると、最終的に1つの eigenstate に収束します。

### <a name="experiment-design"></a>実験の設計

に渡された $t $ と反転角度 $ \ シータ $ の測定時間は、 `oracle` *パーティクル推測のヒューリスティック* 、\begin{align} (-phi)、および \variance{\phi}}. に従って選択されます。 {1}
\end{align} このヒューリスティックは、予期される事後分散を、標準の前提条件下で反復フェーズ推定で削減するのに最適です。

### <a name="optimality"></a>たいてい

この操作では、2次損失 $L (\ phi, \hat{\phi}) \mathrel{: =} (\hat{\phi}) ^ 2 $ を使用して評価された、フェーズ $/phi $ の最適な推定に近似されます。

反復フェーズ推定の統計の詳細については、「 [ベイジアンフェーズの推定](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 」を参照してください。

## <a name="references"></a>関連項目

- Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6)、 [arxiv: 1110.3067](https://arxiv.org/abs/1110.3067)。
- Wiebe *2013* [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)、 [arxiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe と Granade 2018 *(準備中)* 。