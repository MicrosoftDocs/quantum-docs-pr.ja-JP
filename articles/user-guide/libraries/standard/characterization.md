---
title: クォンタムの特性と統計
description: フェーズの予測からの測定統計を使用して、クォンタムプログラミングの結果値を推定する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7ed92c29020ccf389faa099f5bd80516af525578
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275767"
---
# <a name="quantum-characterization-and-statistics"></a>クォンタムの特性と統計 #

実用的なクォンタムアルゴリズムを開発するために、操作の効果を特徴付けることが重要です。
これは、クォンタムシステムのすべての測定値が1ビットの情報を生成するため、困難です。
このような概念を表すために必要な多くの情報をユーザーが収集できるように、1つのクォンタム状態だけを使用して、eigenvalue を学習するには、多くの測定の結果を合成する必要があります。
クォンタムの状態は特に厄介です。これは、[複製なしの定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)は、状態のコピーを作成できるようにするため、状態の1つのコピーから任意のクォンタム状態を学習する方法がないことを示すためです。
ユーザーからのクォンタム状態のこのような難読化は、Q # がプログラムを量子*化するか*どうかの状態を公開しないという事実に反映されています。
このため、操作と状態を黒色のボックスとして扱うことによって、クォンタムの特性を解決します。このアプローチは、クォンタムの特性、検証、検証 (QCVV) の実験的プラクティスによく似ています。

特性は、前に説明した他の多くのライブラリとは異なります。
ここでの目的は、状態ベクターでのユニタリ変換を実行するのではなく、システムに関する古典的な情報を学習することです。
したがって、これらのライブラリは、クラシック情報とクォンタム情報の両方の処理をブレンドする必要があります。


## <a name="iterative-phase-estimation"></a>反復フェーズの推定 ##

クォンタムの特性に関してクォンタムプログラミングを見ると、クォンタムフェーズの推定に代わる便利な方法となります。
つまり、$n $-qubit レジスタにクォンタムフェーズの推定と同様にフェーズのバイナリ表現を含めるように準備するのではなく、*クラシック*エージェントが測定を使用してクォンタムシステムのプロパティを学習するプロセスとして、フェーズ推定を表示できます。
ここでは、フェーズ kickback を使用して、ブラックボックスの操作のアプリケーションを不明な角度で回転させますが、回転の直後の各手順で回転する ancilla qubit を測定します。
これには、クォンタムケースで説明されているフェーズ kickback を実行するために1つの追加の qubit だけが必要であるという利点があります。そのため、各ステップの測定結果から反復的な方法を学習します。  
以下の各方法では、実験を設計するためのさまざまな戦略と、フェーズを学習するためのさまざまなデータ処理方法を使用します。  各ユーザーには、厳密なエラーの範囲、前の情報の組み込み、エラーの許容、メモリ limitted の古典コンピューターでの実行など、それぞれ固有の利点があります。

反復的なフェーズの推定については、ブラックボックスの操作として指定された $U $ のユニタリが考慮されます。
[データ構造](xref:microsoft.quantum.libraries.data-structures)の oracles に関するセクションで説明されているように、Q # キャノンは、 <xref:microsoft.quantum.oracles.discreteoracle> タプル型によって定義されたユーザー定義型による演算を実行し `((Int, Qubit[]) => Unit : Adjoint, Controlled)` ます。
の場合、具体的に、の場合は `U : DiscreteOracle` `U(m)` $U ^ m $ を実装し `m : Int` ます。

この定義では、反復フェーズの推定の各手順は、$ \ket{+} $ 状態の補助 qubit と初期状態 $ \ket{\phi} $ を準備しています。これは、$U [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) (m) $、つまり $U (m) \ket{\phi} = e ^ {im/phi} \ k {\ phi} $ と想定されています。  
その後、の制御されたアプリケーションを `U(m)` 使用して、$ left (R \_ 1 (m) \ket{+} \ right) \ket{\phi} $ という状態を準備します。
クォンタムの場合と同様に、oracle の制御されたアプリケーションの効果は、 `U(m)` $ \ket{+} $ の不明なフェーズに対して $R _1 $ を適用した場合の効果とまったく同じです。そのため、$U $ の効果をこの簡単な方法で記述できます。
必要に応じて、アルゴリズムは $R _1 (-m-シータ) $ を適用してコントロール qubit を回転させます。これにより、$ \ket{\psi} = \ left (R \_ 1 (m [\phi-\theta]) \ket{+} \ right) \ket{\phi} $ $ という状態が取得されます。
のコントロールとして使用される補助 qubit `U(m)` は、1つのクラシックを取得するために $X $ 単位で測定され `Result` ます。

この時点で、 `Result` 反復フェーズ推定によって取得された値からフェーズを再構築することは、従来の統計的な推論の問題です。
修正された推論方法で得られた情報を最大限に活用する $m $ の値は、単に統計の問題です。
この問題を解決するために、Q # キャノンで提供される統計アルゴリズムの説明に進む前に、ベイジアンパラメーターの推定形式の理論レベルで反復フェーズ推定を簡単に説明します。

### <a name="iterative-phase-estimation-without-eigenstates"></a>Eigenstates のない反復フェーズ推定 ###

Eigenstate ではない入力状態が指定されている場合、たとえば $U (m) \ket{\phi \_ j} = e ^ {im/phi \_ j} $ の場合、フェーズ推定のプロセスによって、クォンタム状態が1つのエネルギー eigenstate に対して非決定的に指示されます。  最終的に収束される eigenstate は、観測されたを生成する可能性が最も高い eigenstate です `Result` 。

具体的には、PE の1つのステップで、状態が \begin{align} \ sum_j \ sqrt{/pr (\ phi j)} \ket{\phi j}/map (\ phi j) に対して、次の非ユニタリ変換が実行されます。 \_ \_ \_ \_ } \ sqrt{\ Pr (\ text{result} | \ phi \_ j)} \Ket{\phi \_ j}} {\ sqrt{/pr (\ phi \_ j) \ sum \_ j/pr (\ text{result} | \ phi \_ j)}}。
\end{align} このプロセスは複数の値に対して反復処理さ `Result` れるため、$ \ prod_k \ Pr (\ text{result} k | \ phi j) $ の最大値を持たない eigenstates \_ \_ は指数関数的に抑制されます。
その結果、推論プロセスは、実験が適切に選択された場合に、1つの eigenvalue を持つ状態に収束する傾向があります。

Bayes ' 定理は、フェーズ推定の結果の状態が \begin{align} \frac{\sqrt{\Pr (\ phi \_ j)} \ sqrt{/Pr (\ text{result} | \ phi j)} \ket{\phi j}} {/sqrtという形式で記述されていることを示唆しています。 \_ \_ {/pr (\ phi \_ j) \ sum \_ j \ pr (\ text{result} | \ phi \_ j)}} = \ sum_j \ sqrt{/pr (\ phi \_ j | \ text{result})} \ket{\phi \_ j}。
\end{align} ここ $ \ Pr (\ phi \_ j |/text{result}) $ は、指定された eigenstates に関する各仮説に対して、ある確率として interpretted にすることができます。

1. 測定前のクォンタムの状態に関する知識
2. $U $ との eigenstates の知識
3. $U $ の固有値の情報。

この3つのことを学習するのは、従来のコンピューターでは指数関数的に困難です。
フェーズの推定のユーティリティは、このようなクォンタムの学習タスクを何も知らずに実行できるという事実から、小さな範囲ではなくなります。
この理由のフェーズ推定は、指数高速化を提供するさまざまなクォンタムアルゴリズムの中で表示されます。

### <a name="bayesian-phase-estimation"></a>ベイジアンフェーズの推定 ###

> [!TIP]
> 実際のベイジアンフェーズ推定の詳細については、 [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)サンプルを参照してください。

ベイジアンフェーズの推定の概念は単純です。
フェーズ推定プロトコルから測定統計を収集した後、ベイジアン推論を使用して結果を処理し、パラメーターの推定値を指定します。
この処理により、その推定値の推定値だけでなく、eigenvalue の推定値も得られます。
また、アダプティブ実験を実行し、前の情報を利用することもできます。
メソッドの原則としての欠点は、コンピューティングの要件が高いことです。

このベイジアン推論プロセスのしくみを理解するために、1つの結果を処理するケースを考えてみましょう `Zero` 。
$X = \ket{+} \ ロウ {+}-\ket \bra $ であることに注意 {-} {-} してください。 $ \ket{+} $ は、に対応する $X $ の唯一の正の eigenstate です `Zero` 。
入力状態が $ \ket{\psi}\ket{\phi} $ であることを指定して、最初の qubit の測定を観察する確率は、 `Zero` $ $ です。 \ Pr (\texttt{Zero} | \ psi) = \ left | \braket{+ | \psi}/right | ^ 2 です。 [ `PauliX` ](xref:microsoft.quantum.concepts.pauli)
\ket{\psi} 反復フェーズ推定の場合は、$ = R_1 (m [\phi-\theta]) \ket{+} $ があります。この場合、\begin{align} \ Pr (\texttt{Zero} | \ phi; m, \ シータ) & = \ left |\braket{+ |R_1 (m [\phi-\theta]) |+} \ right | ^ 2 \\ \\ & = \ left | \frac12 \ left (\bra {0} + \bra {1} \ right) \ left (\ket {0} + e ^ {i m [\phi-\theta]} \ket/ {1} right) \ right | ^ 2 \\ \\ & = \ left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \ right | ^ 2 \\ \\ & = \ cos ^ 2 (m [\phi-\theta]/2) \ tag{★} \ label{eq:}。
\end{align} は、反復的なフェーズ推定は、決まる正弦波関数の振幅頻度を学習することで構成されます。これにより、コインをその sinusoid によって指定されたバイアスと反転させることができます。
従来の古典的な用語の後で、$ \eqref{eq: フェーズ-予測確率} $ を呼び出して、反復フェーズ推定の*尤度関数*を呼び出します。

`Result`反復フェーズの推定確率関数を観察した後、Bayes のルールを使用して、その観測に従っていると判断する必要があることを規定することができます。
具体的に、\ begin{\frac{\Pr} \ pr (-phi | d) = (d | \ phi) \ pr (\ phi)} {\ int \ pr (d | \ phi) \ pr (& phi) {\mathrm d} \phi}/pr (¥ phi)、\ end{ \\ \Texttt{Zero}, \texttt{One}} $ の場合は、\ end{,} \\ $ はで、$ \ `Result` Pr (\ phi) $ は以前の信条について説明します。 $d
これにより、反復フェーズ推定の反復的な性質が明示的になります。事後 distribution $ \ Pr (-phi | d) $ は、次の観測の直前にある信条について説明し `Result` ます。

この手順のどの時点でも、クラシックコントローラーによって推論されたフェーズ $ \hat{\phi} $ を、\hat{\phi} \mathrel{として報告できます。 =} \ 期待 [\ phi | \ text{data}] = \ int \ phi \ Pr (\ phi | \ text{data}) {\mathrm d}/phi, \ end{の場合、$ \ text{data} $ は取得されたすべての値のレコード全体を表し `Result` ます。

正確なベイジアン推論は、実際には困難です。
これを確認するには、$ bit 変数 $x $ $n を学習します。
以前のディストリビューション $ \ Pr (x) $ は $x $ の $ 2 ^ n $ 仮定値をサポートしています。
つまり、$x $ の推定精度が高い場合、ベイジアンフェーズの推定には、膨大なメモリと処理時間が必要になることがあります。
クォンタムシミュレーションなどの一部のアプリケーションでは、必要な limitted の精度によって、そのような方法では、Shor のアルゴリズムなどの他のアプリケーションでは、そのフェーズの推定手順で正確なベイジアン推論を使用できません。  このため、[ランダムウォークフェーズの推定 (RWPE)](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation)や、[堅牢なフェーズの推定](xref:microsoft.quantum.characterization.robustphaseestimation)などの非ベイジアンアプローチについても、おおよそのベイジアンメソッドの実装を提供しています。

### <a name="robust-phase-estimation"></a>堅牢なフェーズの推定 ###

測定結果からのフェーズの見積もりの*posteriori*ベイジアン再構築の最大数は、最悪の場合には指数関数的に難しくなります。 このため、ほとんどの実用的なフェーズ推定アルゴリズムでは再構築の一部の品質を犠牲にしています。これは従来の後処理の多くを反映しています。これにより、polynomially は、実行される測定値に応じてスケーリングされます。

このような従来の処理後の手順の例として、[堅牢なフェーズ推定アルゴリズム](https://arxiv.org/abs/1502.02677)と、上記の署名と入力があります。 この例では、入力の $U が $ $ が型としてパッケージ化されていることを前提 `DiscreteOracle` としています。したがって、制御された $U $ の整数の累乗のみをクエリします。 レジスタ内の入力状態 `Qubit[]` が eigenstate $U \ket{\psi} = e ^ {i\ phi} \ k {\ psi} $ の場合、堅牢なフェーズの推定アルゴリズムはとして $/phi $ の推定 $ \hat{\phi}\in [-\ pi, \ pi) を返し `Double` ます。

堅牢なフェーズの推定の最も重要な機能は、他の多くの便利なバリエーションと共有されています。 $ \hat{\phi} $ の再構築の品質は、意味のあるハイゼンベルグに限定されています。 つまり、true 値から $ \hat{\phi} $ の偏差が $-シグマ $ の場合、$/シグマ $ はクエリの合計数に反比例しています。これは、制御された $U $ (つまり、$ \ シグマ = \mathcal{O} (1/Q) $) に対して作成された $Q クエリの合計数に比例します。 現在、偏差の定義は、異なる推定アルゴリズムによって異なります。 場合によっては、$ \mathcal{O} (1) の確率が少なくとも、推定エラー $ | \hat{\phi}-\phi | \_ であることを意味することがあります。\circ\le、シグマ $、いくつかの循環メジャー $ \ circ $。 堅牢なフェーズの推定については、周期的な差異は、厳密には $-シグマ ^ 2 = \mathbb{E} \_ \hat{\phi} [( \_ -mod {2 \ pi} (\hat{\phi}-\phi +-pi)--pi) ^ 2] $ になります。これは、周期的なフェーズを1つの有限の間隔 $ (-\ pi, lt pi] $ にラップ より正確に言えば、堅牢なフェーズの推定の標準偏差は、不等ず $ $ \begin{align} 2.0 \ pi/Q/\end{align} $ {n}/le 10.7 \ pi/Q, $ $ に適合します。下限は asymptotically large $Q $ の上限に達し、上限は小さいサンプルサイズでも保証されます。  入力によって選択された $ $n、$Q $ を暗黙的に定義することに注意して `bitsPrecision` ください。

関連するその他の詳細には、たとえば、$1 $ ancilla qubit だけの小さな領域のオーバーヘッド、またはプロシージャが非アダプティブであることを意味します。つまり、必要なクォンタム実験のシーケンスは、中間測定結果に依存しません。 この後の例では、フェーズ推定アルゴリズムの選択が重要であるため、1つは、などのドキュメントと、その @"microsoft.quantum.characterization.robustphaseestimation" 実装に関する詳細情報と参照されるパブリケーションを参照する必要があります。

> [!TIP]
> 堅牢なフェーズ推定を使用するサンプルは多数あります。 さまざまな物理システムのグラウンドステートエネルギーを抽出するフェーズの推定については、「 [ **H2 シミュレーション**のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)」、「 [ **simpleising**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)」、および「" [**モデルのモデル**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)化" サンプルを参照してください。


### <a name="continuous-oracles"></a>継続的 Oracles ###

また、前に使用した oracle モデルから汎用化して、キャノンの種類でモデル化された継続時間の oracles を実現することもでき <xref:microsoft.quantum.oracles.continuousoracle> ます。
1つのユニタリ演算子ではなく $ $U、$U (t) U (s) $ = $U (t + s) $ のように、\mathbb{R} $ の $t \ の $U (t) $ の一連のユニタリ演算子を使用します。
これは、個別のケースよりも弱いステートメントです <xref:microsoft.quantum.oracles.discreteoracle> \, 。固定の $ \ デルタ t $ に対して $t = m \ デルタ t $ を制限することによってを構築できるためです。
$U (t) = \ exp (i H t) $ in a operator $H $ ($ \ exp $[は、](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups) [「高度なマトリックス](xref:microsoft.quantum.concepts.matrix-advanced)」で説明されているマトリックス指数)。
$H $ の eigenstate $ \ket{\phi} $ ($H \ket{\phi} = \ phi \ket{\phi} $ は、すべて $t $, \ begin{\ket{\phi}.} U (t) \ket{\phi} = e ^ {i \ phi t} に対して $U (t) $ という eigenstate も使用されます。
\end{equation}

[ベイジアンフェーズの推定](#bayesian-phase-estimation)について説明したのとまったく同じ分析を適用できます。また、尤度関数は、このより一般的な oracle モデルとまったく同じです。 $ $ \ Pr (\texttt{Zero} | + phi; t,-シータ) = \ cos ^ 2 \ left (\frac{t [\ phi--シータ]} {2} \ right)。
さらに、$ $ $U $ は、 [Hamiltonian シミュレーション](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)の場合と同様に、$/phi $ をエネルギーとして解釈します。
したがって、継続的なクエリでフェーズ推定を使用すると、$t $ を整数にする必要があるため、選択した実験を損なうことなく、分子、[マテリアル](https://arxiv.org/abs/1510.03859)、または[フィールド理論](https://arxiv.org/abs/1111.3633v2)のシミュレートされた[エネルギー](https://arxiv.org/abs/quant-ph/0604193)範囲を学習できます。

### <a name="random-walk-phase-estimation"></a>ランダムウォークフェーズの推定 ###

Q # では、反復フェーズ推定から取得されたデータレコードに対してランダムウォークを使用して動作するクォンタムデバイスの近くに使用するように設計された、ベイジアンフェーズ推定についての実用的な概算を提供しています。
このメソッドは、アダプティブで完全に決定的であり、メモリオーバーヘッドが非常に少ない推定フェーズ $ \hat{\phi} $ でのエラーのほぼ最適化されたスケーリングを可能にします。

このプロトコルでは、前の分布がガウスであることを前提として、おおよそのベイジアン推論方法が使用されます。
このガウス想定では、事後 variance を最小にする実験に分析式を使用できます。
次に、その実験の結果に基づいて、$ + phi $ の見積もりを事前に決められた量だけ左または右にシフトし、事前に決められた量だけ分散を縮小します。
この平均と分散によって、次の実験で $/phi $ の前にガウスを指定するために必要なすべての情報が得られます。
予期しない測定エラーが発生した場合、または初期の前に true が発生した場合、このメソッドは失敗する可能性があります。
現在の平均と標準偏差がシステムに適しているかどうかをテストする実験を実行することで、障害から復旧します。
それ以外の場合、アルゴリズムはウォークの逆の手順を実行し、プロセスは続行されます。
また、後方にステップ実行する機能により、初期の標準偏差が inapropriately 小さい場合でもアルゴリズムが学習できるようになります。

## <a name="calling-phase-estimation-algorithms"></a>フェーズ推定アルゴリズムの呼び出し ##

Q # キャノンによって提供される各フェーズの推定操作では、最終的な推定値 $ \hat{\phi} $ から得られる品質をパラメーター化します。
ただし、これらのさまざまな入力では、複数の入力が共通に共有されるため、品質パラメーターに対する部分的なアプリケーションによって共通のシグネチャが生成されます。
たとえば、次の <xref:microsoft.quantum.characterization.robustphaseestimation> セクションで説明する操作には次のシグネチャがあります。

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision`入力はに固有で `RobustPhaseEstimation` あり、 `oracle` と `eigenstate` は共通です。
そのため、 **H2Sample**に示されているように、操作は、 `(DiscreteOracle, Qubit[]) => Unit` ユーザーが任意のフェーズ推定アルゴリズムを指定できるように、フォームの入力と共に反復フェーズ推定アルゴリズムを受け入れることができます。

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

これらの多様なフェーズの推定アルゴリズムは、さまざまなプロパティと入力パラメーターに対して最適化されています。これは、ターゲットアプリケーションに最適な選択を行うために理解する必要があります。 たとえば、一部のフェーズ推定アルゴリズムはアダプティブです。つまり、将来の手順は、前の手順の測定結果によってクラシックデプロイ制御されます。 一部の機能では、任意の実数の累乗によってブラックボックスの exponentiate を計算する機能が必要であり、他のユーザーは整数の累乗のみを必要としますが、フェーズ推定剰余 $ 2 \ pi $ のみを解決できます。 多くの補助 qubits が必要であり、他のユーザーには1つしか必要ありません。

同様に、ランダムウォークフェーズの推定の使用は、キャノンで提供される他のアルゴリズムとほぼ同じように行われます。

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
