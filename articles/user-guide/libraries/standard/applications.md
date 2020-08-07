---
title: 標準ライブラリ内のアプリケーション Q#
description: クォンタムコンピューティングの2つの基本的なアプリケーション (Hamiltonian シミュレーションと Shor の検索アルゴリズム) について説明します。
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4caacaad127f8a4d3b6f77efe35ebe7d3b97cacf
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868765"
---
# <a name="applications"></a>アプリケーション #

## <a name="hamiltonian-simulation"></a>ハミルトニアン シミュレーション ##

クォンタムシステムのシミュレーションは、クォンタム計算の最も優れたアプリケーションの1つです。
従来のコンピューターでは、クォンタム機構をシミュレートするのが困難です。一般に、ディメンション $N、その状態ベクトル表現の $ を使用してスケーリングします。
この表現は $n $ qubits $N = 2 ^ n $ の数で指数関数的に増加するため、[次元の curse](xref:microsoft.quantum.concepts.multiple-qubits)とも呼ばれる特徴は困難です。

ただし、この状況は、quantum ハードウェアでは大きく異なる可能性があります。 クォンタムシミュレーションの最も一般的なバリエーションは、時間に依存しない Hamiltonian シミュレーションの問題と呼ばれます。 ここには、Hermitian マトリックスである system Hamiltonian $H $ の説明と、クォンタムコンピューター上の $n $ qubits で何らかの基準としてエンコードされた初期クォンタム状態 $ \ket{\psi (0)} $ の説明が含まれています。 Closed システムのクォンタム状態は、Schrödinger 式 $ $ \begin{align} i\ket{\psi {d (t)}} {d t} & = H \ket{\psi (t)} の下で進化しています。 \end{align} $ $ 目標は、\ket{\psi (t)} = U (t) \ket{\psi (0)} $ が Schrödinger の式を解決できるように、特定の時刻に (t) = e ^ {-iht} $ という $U (t) = e ^ {-iht} $ を実装することです。 $t
と同様は、時間に依存する Hamiltonian シミュレーションの問題は同じ方程式を解決しますが、$H (t) $ は time の関数になりました。

Hamiltonian のシミュレーションは、他の多くのクォンタムシミュレーションの問題の主要なコンポーネントであり、Hamiltonian シミュレーションの問題の解決策としては、おおよそのからに対するプリミティブなクォンタムゲートのシーケンスを示すアルゴリズムがあります。これは、 \\ \\ [スペクトル基準](xref:microsoft.quantum.concepts.matrix-advanced)でエラー $ | \tilde{U}-U (t) |/le/イプシロン $ を使用します。 これらのアルゴリズムの複雑さは、対象の Hamiltonian の説明が quantum コンピューターからアクセスできるようにする方法に非常に大きく依存しています。 たとえば、最悪の場合、$n $ qubits の $H $ が $ 2 ^ n/times 2 ^ n $ n $ number のリストとして指定された場合 (各マトリックス要素に1つ)、単にデータを読み取るだけで、既に指数関数が必要になります。 最良のケースでは、\ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ が問題を解決できるように、ブラックボックスのユニタリにアクセスする $O ことを前提としています。 これらの入力モデルはいずれも特に興味深いものではありません。従来のアプローチよりも優れていません。後者の場合は、その実装のプリミティブゲートの複雑さが隠されています。

### <a name="descriptions-of-hamiltonians"></a>Hamiltonians の説明 ###

そのため、入力の形式に関する追加の前提条件が必要です。 実際の物理システムや興味深い計算の問題の場合や、量子コンピューターで効率的に実装できるように十分に制限されている入力モデルなど、興味深い Hamiltonians を含む入力モデルの場合は、細かいバランスを取る必要があります。 この資料には、さまざまな簡単な入力モデルが含まれている場合があります。 

クォンタム入力モデルの例として、[サンプルベースの Hamiltonian シミュレーション](http://www.nature.com/articles/s41534-017-0013-7)は、密度マトリックス $ \rho $ のコピーを生成するクォンタム操作へのブラックボックスアクセスを想定しています。これは、Hamiltonian $H $ として使用されます。 [ユニタリアクセスモデル](https://arxiv.org/abs/1202.5822)では、Hamiltonian ではなく、unitaries $ $ \begin{align} H & = \ sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j, \end{align} $ $a $ として、分解され \_ j>$0 が係数、$ \hat{U} \_ j $ は unitaries います。 次に、1つのには、必要な $ \hat{U} j $ を選択する、\ket{j}\bra{j}\otimes = \ sum ^ {d-1} {j = 0} \hat{U} j $ という、1つのブラックボックスへ $V のアクセスがあることを前提としています。 \_ \_ \_ oracle $A \ket {0} = \ sum ^ {d-1} \_ {j = 0} \ sqrt{j \_ /\ sum ^ {d-1} \_ {k = 0} \ alpha \_ j} \ket{j} $ は、これらの係数をエンコードするクォンタム状態を作成します。 [スパース Hamiltonian シミュレーション](https://arxiv.org/abs/quant-ph/0301023)の場合、1つは、Hamiltonian がすべての行で $d = \mathcal{O} (\Text{polylog} (N)) $ 0 以外の要素のみを含むスパースマトリックスであることを前提としています。 さらに、これらのゼロ以外の要素の場所とその値を出力する効率的なクォンタム回線があることを前提としています。 [Hamiltonian シミュレーションアルゴリズム](xref:microsoft.quantum.more-information)の複雑さは、これらのブラックボックスに対するクエリ数の観点で評価されます。プリミティブゲートの複雑さは、これらの黒いボックスを実装する難しさに大きく依存します。

> [!NOTE]
> ビッグ I/o 表記は、アルゴリズムの複雑さのスケーリングを説明するためによく使用されます。 2つの実関数 $f g $ では、式 $g (x) = \mathcal{O} (f (x)) $ は、 \_ すべての $0 $g に対して $x (x) \ le c f (x) $ が使用されるように、正の正の定数 $x 0、c>$0 が存在することを意味し \_ ます。 

クォンタムコンピューターに実装するほとんどの実用的なアプリケーションでは、これらのブラックボックスは、$ \mathcal{O} (\text{polylog} (N)) $ プリミティブ量子ゲートを使用して、効率的に実装できなければなりません。 より厳密で効率的に simulable Hamiltonians には、古典的な従来の説明が十分にある必要があります。 このような定式化では、Hamiltonian 分解されが Hermitian parts $ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} H_j の合計になると想定されています。
\end{align} $ $ では、Hamiltonian $H j $ の各部分は簡単にシミュレートできると想定されてい \_ ます。 これは、すべての時間に対して、$e ^ {-iH \_ j t} $ が $t $ \mathcal{O} (1) $ プリミティブ量子ゲートを使用して正確に実装できることを意味します。 たとえば、これは特殊なケースでは、各 $H \_ j $ がローカルの P\mathcal{O} li 演算子であることを意味します。つまり、空間的な終値で動作する $ (1) $ 非 Id p li 演算子のすべての製品であることを意味します。 このモデルは、条件の数が $d = \mathcal{O} (\text{polylog} (N)) $ であるため、制限されたローカルの相互作用を持つ物理システムに特に適用されます。また、クラシックデプロイについて説明されているように、多項式時間で明確に記述することもできます。

> [!TIP]
> パートの合計に分解する Hamiltonians は、Dynamical Generator 表現ライブラリを使用して記述できます。 詳細については、「Dynamical Generator 表現」の「[データ構造](xref:microsoft.quantum.libraries.data-structures)」を参照してください。

### <a name="simulation-algorithms"></a>シミュレーションアルゴリズム ###

クォンタムシミュレーションアルゴリズムでは、Hamiltonian の指定された説明を、Hamiltonian と呼ばれるおおよその時間の推移的な一連のプリミティブクォンタムゲートに変換します。

Hamiltonian 分解されが Hermitian パーツの合計になる特殊なケースでは、Trotter Suzuki 分解は、Hamiltonians コンポーネントの合計に分解される Hermitian をシミュレートするための、特にシンプルで直感的なアルゴリズムです。 たとえば、このファミリのファーストオーダーインテグレーターは、$ $ \begin{align} U (t) & = \ left (e ^ {-iH 0 t/r} \_ e ^ {-ih \_ 1 t/r}/cドット e ^ {-ih \_ {d-1} t/r} \ right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r)、\end{align} $ $ を使用して $r d $ terms の製品を使用します。 

> [!TIP]
> サンプルでは、Trotter-Suzuki シミュレーションアルゴリズムのアプリケーションについて説明します。
> 各ターゲットコンピューターによって提供される組み込み操作のみを使用する場合は、 [ **simpleising**サンプル](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple)を参照してください。
> Trotter-Suzuki library コントロール構造体を使用する場合は、 [ **IsingTrotter**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution)を参照してください。
> Trotter-Suzuki library コントロール構造体を使用した分子 Hydrogen については、「 [ **H2 シミュレーション**のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)」を参照してください。

多くの場合、シミュレーションアルゴリズムを実装する必要がありますが、その実装の詳細には関心がありません。 たとえば、2番目の命令インテグレーターは、$ $ \begin{align} U (t) & = \ left (e ^ {-iH \_ 0 t/2r} e ^ {-ih \_ 1 t/2r}/cドット e ^ {-ih \_ {d-1} t/2r} を近似します。 e ^ {-ih \_ {d-1} t/2r} \ cドット e ^ {-ih \_ 1 t/2r} e ^ {-ih \_ 0 t/2r} \ 右) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ |H \_ j \\ | ^ 3 t ^ 3/r ^ 2)、$ 2rd $ terms の製品を使用する \end{align} $ $。 注文が大きいほど、さらに多くの用語と最適化されたバリエーションが必要になることがあります。その場合、指数には非常に重要な順序が必要になります 他の高度なアルゴリズムでは、中間ステップで ancilla qubits を使用することが必要になる場合もあります。 そのため、ユーザー定義型として、キャノンのシミュレーションアルゴリズムをパッケージ化します。

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

最初のパラメーターは `Double` シミュレーションの時間で、データ構造の Dynamical Generator 表現セクションに記載されている2番目のパラメーターは、 `EvolutionGenerator` 時間に依存しない Hamiltonian の典型的な説明であり、Hamiltonian の各用語は、クォンタム回線によってシミュレートされる方法についての指示と共にパッケージ化されます。 [data-structures](xref:microsoft.quantum.libraries.data-structures) このフォームの型では、3番目のパラメーターに対して、( `Qubit[]` シミュレートされたシステムのクォンタムの状態を格納するレジスタである) 3 番目のパラメーターに対して、$e におおよその単位が指定されています。 時間に依存する場合と同様に、ユーザー定義型は `EvolutionSchedule` 、時間に依存する Hamiltonian の従来の説明である型を使用して定義します。

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

例として、Trotter Suzuki 分解は、次のキャノン関数を使用して呼び出すことができます。パラメーターを使用すると、 `trotterStepSize` 各指数のシミュレーション期間と、 `trotterOrder` 目的のインテグレーターの順序を変更できます。

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> シミュレーションライブラリのアプリケーションについては、「」のサンプルで説明されています。 を使用した表示モデルのフェーズ推定については `SimulationAlgorithm` 、 [ **IsingPhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)を参照してください。
> を使用した adiabatic モデルでの状態の準備の詳細について `TimeDependentSimulationAlgorithm` は、 [ **AdiabaticIsing**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic)を参照してください。


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic 状態の準備 & フェーズの推定 ###

Hamiltonian シミュレーションの1つの一般的なアプリケーションは、adiabatic 状態の準備です。 ここでは、2つの Hamiltonians $H \_ {\ text{startno} $ と $H \_ {\ text{endno} $ と、start Hamiltonian $H \_ {\ text{start{1}} $ のグラウンド状態であるクォンタム状態 $ \ket{\psi (0)} $ を使用して提供されています。 通常、$H \_ {\ text{startno} $ が選択されているため、$ \ket{\psi (0)} $ はコンピューティングベースの状態 $ \ket{0\cdots 0} $ から簡単に準備できます。 時間に依存するシミュレーションの問題でこれらの Hamiltonians 間を補間することによって、最終的な Hamiltonian $H \_ {\ text{end{2} $ の最上位の状態になる可能性が高くなります。 Hamiltonian のグランド州に対して十分な概算を準備することで、時間に依存する Hamiltonian シミュレーションアルゴリズムでサブルーチンとしてを呼び出すことによって、この方法で処理を進めることができますが、その他の概念的に異なる手法 eigensolver などが考えられます。

しかし、量子化学に存在する別のアプリケーションは、化学の反応の中間手順を表す Hamiltonians のグラウンドステートエネルギーを推定することです。 たとえば、このようなスキームでは、adiabatic 状態の準備に依存してグラウンド州を作成し、時間に依存しない Hamiltonian シミュレーションをフェーズ推定の特性のサブルーチンとして組み込んで、有限のエラーと成功の確率でこのエネルギーを抽出できます。 

シミュレーションアルゴリズムをユーザー定義型として抽象化し、その `SimulationAlgorithm` `TimeDependentSimulationAlgorithm` 機能をより高度なクォンタムアルゴリズムに簡単に組み込むことができるようにします。 これは、一般的に使用されるサブルーチンに対して同じことをためします。

そのため、便利な関数を定義します。

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

これにより、adiabatic 状態準備のすべてのステップを実装する、ユニタリ操作が返されます。 最初のパラメーターは、 `interpolatedTime` 2 番目のパラメーターによって記述される開始 Hamiltonian `evolutionGeneratorStart` と3番目のパラメーターによって記述される end Hamiltonian との間で線形に補間を補間する時間を定義し `evolutionGeneratorEnd` ます。 4番目のパラメーターで `timeDependentSimulationAlgorithm` は、シミュレーションアルゴリズムを選択します。 `interpolatedTime`が十分に長い場合、初期のグラウンド状態は、時間に依存するシミュレーションの期間全体にわたって Hamiltonian の瞬時の接地状態を維持するため、終了 Hamiltonian のグラウンドの状態で終了します。

また、一般的な量子化学実験のすべての手順を自動的に実行する便利な操作も定義します。 たとえば、次のものがあります。これにより、adiabatic 状態の準備によって生成された状態のエネルギー見積もりが返されます。

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits`クォンタムの初期状態をエンコードするために使用される qubits の数です。 `statePrepUnitary`計算基準 $ \ket{0\cdots 0} $ から開始状態を準備します。 `adiabaticUnitary`は、関数によって生成されるように、adiabatic 状態の準備を実装する、ユニタリ操作です `InterpolatedEvolution` 。 `qpeUnitary`結果として得られるクォンタムの状態に対してフェーズ推定を実行するために使用される、ユニタリ操作です。 `phaseEstAlgorithm`フェーズ推定アルゴリズムを選択します。

> [!TIP]
> Adiabatic の状態準備のアプリケーションについては、「」のサンプルで説明されています。 Adiabatic 状態の準備と関数の使用を手動による実装を使用している場合は、 `AdiabaticEvolution` [ **AdiabaticIsing**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic)を参照してください。
> Adiabatic モデルでのフェーズの推定と状態の準備については、 [ **IsingPhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)を参照してください。

> [!TIP]
> [分子 Hydrogen のシミュレーション](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)は、興味深い簡単なサンプルです。 O'Malley で報告されるモデルと実験結果[。](https://arxiv.org/abs/1512.06860) に必要なのは、Pの Li マトリックスだけで、$ \ hat H = g \_ {0} I \_ 0i \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {Z \_ 1} + g \_ 3 {z \_ 0} {z 1} + g \_ \_ 4 {y 0} { \_ y \_ 1} + g \_ 5 {x \_ 0} {x \_ 1} $ です。 これは、2つの Hydrogen アトムの間の距離 $R $ から計算される定数 $g $ が2つの qubits のみを必要とする有効な Hamiltonian です。 キャノン関数を使用すると、Paulis は unitaries に変換され、その後、Suzuki 分解を使用して短時間に進化します。 _2 $ グラウンドの状態に $H 対しては、adiabatic 状態の準備を使用せずに作成することができます。そのため、キャノンからのフェーズの推定を利用して、グラウンドの状態エネルギーを直接見つけることができます。

## <a name="shors-algorithm"></a>Shor のアルゴリズム ##
Shor のアルゴリズムは、quantum コンピューターを使用して重要なクラシックデプロイ困難問題を解決できることを示しているため、クォンタムコンピューティングにおける最も重要な開発の1つです。
Shor のアルゴリズムは、量子コンピューターを使用して大きな数値を因数分解するための高速な方法を提供します。これは*ファクタリング*と呼ばれる問題です。
現在の日常的な暗号システムのセキュリティは、ファクタリングのための高速アルゴリズムが存在しないという前提に基づいています。
そのため、シャードまたはのアルゴリズムは、クォンタム後の世界におけるセキュリティに対する考え方に大きな影響を与えていました。

Shor のアルゴリズムは、ハイブリッドアルゴリズムと考えることができます。
クォンタムコンピューターは、期間検索と呼ばれる計算ハードタスクを実行するために使用されます。
次に、期間を検索した結果がクラシックデプロイに処理され、係数が算出されます。
次の2つの手順を確認します。

### <a name="period-finding"></a>期間の検索 ###

クォンタムのフーリエの変革とフェーズの推定がどのように動作するかを見てきました (「[クォンタムアルゴリズム](xref:microsoft.quantum.libraries.standard.algorithms)」を参照)。これらのツールを使用して、*期間検索*と呼ばれるクラシックデプロイハード計算の問題を解決できます。  次のセクションでは、期間の検索をファクタリングに適用する方法を説明します。

$ と $N $ $a 2 つの整数が指定されています。ここで $a<N $ の場合は、期間を検索することを目標と_してい_ます。 n $ の場合、$r $ は $a $ {mod {Mod} N $ の最小正の整数として定義されます。  

クォンタムコンピューターを使用して注文を検索するには、次の数値演算に適用されているフェーズ推定アルゴリズムを使用できます。 $U _a $: $ $ U_a \ket{x} \equiv \ket{(ax) \ text{mod} N}。 $ $ $U の固有ベクトルは、整数 _a $ および $ 0 \ $1 leq になります。 $ $ \ket{x_s} \equiv 1/\ sqrt{r} \ sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pi i sk} {r}} \ket{a ^ k\ text {mod} N}、$ $ は $U _a $ の_eigenstates_です。
$U _a $ の固有値は $ $ U \_ a \ket{x \_ s} = e ^ {2 \ pi i s/r} \ket{x \_ s} です。 $$

フェーズの推定では、固有値 $e ^ {2 \ pi i s/r} $ が出力されます。この場合、$r $ は $s/r $ の[継続分数](https://en.wikipedia.org/wiki/Continued_fraction)を使用して効率的に学習できます。

クォンタム期間を検索するためのサーキットダイアグラムは次のとおりです。

![クォンタム期間の検索のサーキットダイアグラム](~/media/QPE.svg)

$ 2n $ qubits は $ \ket $ に初期化され {0} $n、$ qubits は $ \ket $ に初期化され {1} ます。
また、このリーダーは、eigenstates を保持するクォンタムレジスタが $ \ket $ に初期化される理由を気にする可能性があります {1} 。
$R $ の順序が事前にわからないため、実際には $ \ket{x_s} $ の状態を直接準備することはできません。
さいわい、$ 1/\ sqrt {r} \ sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket $ ということがわかりました {1} 。
実際に $ \ket{x} $! を準備する必要はありません。
状態が $ \ket $ の $n $ qubits のクォンタムレジスタを準備するだけで済み {1} ます。 

回路には、QFT および複数の制御されたゲートが含まれています。
QFT ゲートについては[既](xref:microsoft.quantum.libraries.standard.algorithms)に説明しました。
制御された $U _a $ gate マップ $ \ket{x} $ to $ \ket{(ax) \ text{mod} N} $ (コントロール qubit が $ \ket {1} $ の場合)。それ以外の場合は $ \ket{x} $ を $ \ket{x} $ にマップします。

$ (A ^ nx) \ text{mod} N $ を実現するには、制御された $U _ {a ^ N} $ を適用します。ここで、$a ^ n \ text{mod} N $ クラシックデプロイを計算して、quantum 回線に接続します。  
このようなモジュール式を実現する回路は、「[クォンタム算術ドキュメント](./algorithms.md#arithmetic)」で説明されています。具体的には、制御された $U \_ {a ^ i} $ 操作を実装するには、モジュール式の累乗回路が必要です。

上記の回線は[クォンタムフェーズ推定](xref:microsoft.quantum.characterization.quantumphaseestimation)に対応しており、順序の検索を明示的に有効にすると、必要な qubits の数を減らすことができます。 [ArXiv: quant-ph/0205095v3 のページ8で](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)説明されているように、Beauregard の方法に従うか、または Microsoft の Quantum で利用可能なフェーズの推定ルーチンの1つを使用できます。 たとえば、[堅牢なフェーズの推定](xref:microsoft.quantum.characterization.robustphaseestimation)では、1つの追加の qubit も使用します。
 
### <a name="factoring"></a>取り入れる ###
要素をファクタリングする目的は、$ $N 整数の2つの素要因を決定することです。 $ は、$ ビットの $n で $N $ です。  
ファクタリングは、以下で説明する手順で構成されています。 これらの手順は、クラシック前処理ルーチン (1-4) という3つの部分に分かれています。$a \ text{mod} N $ (5) の順序を検索するためのクォンタムコンピューティングルーチン。また、従来の後処理ルーチンを通じて、順序から素数を導き出します (6-9)。

従来の前処理ルーチンは、次の手順で構成されています。
1. $N $ が偶数の場合は、素数 $2 $ を返します。
2. $N = p ^ q $ for $p \ geq1 $、$q-geq2 $ の場合は、素数 $p $ を返します。  このステップはクラシックデプロイに実行されます。
3. $1 < a < N-$1 である $a $ の乱数を選択します。
4. $ \ Text{gcd} (a, N) >$1 の場合は、素数 $ \ text{gcd} (a, N) $ を返します。 このステップは、互除法のアルゴリズムを使用して計算されます。
素数が返されない場合は、クォンタムルーチンに進みます。
5. クォンタム期間検索アルゴリズムを呼び出して、$r $ of $a \ text{mod} N $ の順序を計算します。 従来の後処理ルーチンで $r $ を使用して、主な要因を決定します。
6. $R $ が奇数の場合は、前処理手順 (3) に戻ります。
7. $R $ が偶数で $a ^ {r/2} =-1 \ text {mod} N $ の場合は、前処理手順 (3) に戻ります。
8. $ \ Text{gcd} (a ^ {r/2} + 1, N) $ が $N $ の重要な要素ではない場合、$-text{gcd} (a ^ {r/2} + 1, N) $ を返します。
9. $ \ Text{gcd} (a ^ {r/2}-1, N) $ が $N $ の重要な要素ではない場合、$-text{gcd} (a ^ {r/2}-1, N) $ を返します。


ファクタリングアルゴリズムは確率論的です。これには、確率が少なくとも1つ含まれています。これは $r $ が偶数であることを示し、^ {r/2} \ neq-1 \ text{mod} N $ を $a して、素数を生成します。  (詳細については、 [Shor のオリジナルペーパー](https://doi.org/10.1109/SFCS.1994.365700)を参照してください[。詳細に](xref:microsoft.quantum.more-information)ついては、「」の*基本的なクォンタム計算*テキストのいずれかを参照してください)。
素数が返されない場合は、単に手順 (1) からアルゴリズムを繰り返します。  $ 試行を $n た後、すべての試行が失敗した確率は、最大で $ 2 ^ {-n} $ になります。
したがって、アルゴリズムを繰り返しても、成功する回数はほとんどありません。
