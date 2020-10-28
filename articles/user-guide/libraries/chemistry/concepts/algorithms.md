---
title: Hamiltonian Dynamics のシミュレーション
description: Trotter-Suzuki の数式と qubitization を使用して Hamiltonian シミュレーションを操作する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: a303d54476e42b98a14c6b452227b0e1346567c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691884"
---
# <a name="simulating-hamiltonian-dynamics"></a>Hamiltonian Dynamics のシミュレーション

Hamiltonian が基本演算子の合計として表現されたら、既知の手法のホストを使用して、dynamics を基本的なゲート操作にコンパイルできます。
Trotter – Suzuki 数式、unitaries の線形組み合わせ、qubitization という3つの効果的なアプローチがあります。
以下の3つのアプローチについて説明し、 Q# Hamiltonian シミュレーションライブラリを使用してこれらのメソッドを実装する方法の具体的な例を示します。


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki 数式
Trotter – Suzuki 数式の背後にあるアイデアは単純なものです。 Hamiltonian を簡単にシミュレートできる Hamiltonians の合計として表現し、その後、これらの単純な evolutions のシーケンスとして、全体的な進化を概算します。
特に、$H = \ sum_ {j = 1} ^ m H_j $ を Hamiltonian にします。
次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $1 $t $。この近似値のエラーはごくわずかになります。
$E ^ {-i H} $ が通常の指数の場合、この近似値のエラーは $O されません (m ^ 2 t ^ 2) $: 0 になります。
このエラーは $e ^ {-iHt} $ が演算子指数であるために発生します。結果として、この数式を使用すると、$ terms _j $H ( *つまり* 、$H _j H_k \n e H_k H_j $ general) ではないことが原因でエラーが発生します。

$T $ が大きい場合でも、Trotter – Suzuki 式を使用して、短時間の一連の手順に分割することで、dynamics を正確にシミュレートできます。
$R $ を時間の進化に使用されるステップの数にします。そのため、各時間ステップは、$t/r $ の時間に実行されます。 次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r)、$ $ は、$ $m t ^ 2/\ イプシロン $ として $r $ のスケールを設定した場合、$-イプシロン>$0 に対して最大 $/イプシロン $ にエラーを加えることを意味します。

エラー条件がキャンセルされるように、一連の演算子指数を構築することで、より正確な概数を作成できます。
最も単純な式、2番目の順序 Trotter-Suzuki 式、$ $ U_2 (t) = \ left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} の形式で取得します ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iht} + O (m ^ 3 t ^ 3/r ^ 2)、$ $ {3/2} t ^ {3/2}//sqrt {\ イプシロン} $ としてスケールする $r $ を選択すると、$-イプシロン>$0 の $-イプシロン $ より小さくすることができます。 $m

さらに上位の数式でも、特に ($ 2k $) $k>$0 の順序は、次のように再帰的に構築できます。 $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t)] ^ 2 U_ {2k-2} ([1-4s_k] t) [U_ {2k-2} (s_k \~ t)] ^ 2 = e ^ {-iht} + O ((m t) ^ {2k + 1}/r ^ {2k})、$ $ where $s _k = (4-4 ^ {1/(2k-1)}) ^ {-1} $。

最も単純なのは、Suzuki によって最初に導入された次の4番目の順序 ($k = $2) 式です。 $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-iht} + O (m ^ 5t ^ 5/r ^ 4)、$ $ where $s _2 = (4-4 ^ {1/3}) ^ {-1} $。
一般に、任意の上位の数式を同様に構築できます。ただし、多くの場合、より複雑なインテグレーターを使用することによって生じるコストは、最も現実的な問題の4番目の順序を超える利点を上回ることになります。

上記の戦略を機能させるためには、$e ^ {-iH_j t} $ の幅広いクラスをシミュレートするためのメソッドが必要です。
ここで使用できる最も単純な Hamiltonians のファミリは、Pare Li 演算子です。
Diagonalized 演算子は、Clifford 操作 (クォンタムコンピューティングの標準ゲート) を使用して実行できるため、簡単にシミュレートできます。
さらに、これらの値が diagonalized されると、それらが作用する qubits のパリティを計算することで、それらの値を見つけることができます。

たとえば、$ $ e ^ {-Ix/otimes X t} = (hotimes H) e ^ {-Iz\ otimes Z t} (hotimes H), $ $ where $ $ e ^ {-i Z/otimes Z t} = \begin{bmatrix} e ^ {-it &} の 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ ここ、$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ and $e ^ {-iht} \ket {01} = e ^ {-it} \ket {01} $。これは、$0 $ のパリティが $0 $ で、ビット文字列 $1 $ のパリティは $1 $ であるという事実の結果として直接確認できます。

指数演算子は Q# 、次の操作を使用して直接実装でき <xref:Microsoft.Quantum.Intrinsic.Exp> ます。
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Fermionic Hamiltonians の場合、 [ヨルダン– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner) は、Hamiltonian を p li 演算子の合計に簡単にマップします。
これは、化学をシミュレートするために、上記のアプローチを簡単に調整できることを意味します。
Jordan-Wigner 表現ですべてのを手動でループするのではなく、次の例では、このようなシミュレーションを化学内で実行する方法について簡単に説明します。
開始点は、コードでクラスのインスタンスとして表現される、Fermionic Hamiltonian の [ヨルダンの Wigner エンコード](xref:microsoft.quantum.chemistry.concepts.jordanwigner) です `JordanWignerEncoding` 。

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

シミュレーションアルゴリズムによって利用されるヨルダン– Wigner 表現形式は、 Q# ユーザー定義型 `JordanWignerEncodingData` です。
内で Q# は、この形式は便利な関数に渡されます。この関数は、 `TrotterStepOracle` Trotter-Suzuki インテグレーターを使用して、その実行に必要なその他のパラメーターに加えて、時間の短縮に関する演算子を返します。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要なのは、この実装では、 [クォンタムコンピューターを使用した電子構造 Hamiltonians のシミュレーション](https://arxiv.org/abs/1001.3855) で説明されているいくつかの最適化を適用し、必要なシングル qubit 回転数を最小限に抑えるためにクォンタム [化学のクォンタムアルゴリズムを改善](https://arxiv.org/abs/1403.1539) し、シミュレーションエラーを減らします。

## <a name="qubitization"></a>Qubitization

Qubitization は、クォンタムウォークからのアイデアを使用して量子力学をシミュレートする、シミュレーションの代替アプローチです。
Qubitization は Trotter 数式よりも多くの qubits を必要としますが、メソッドは、進化時間と誤差許容範囲に応じて最適なスケーリングを保証します。
このような理由から、一般的な Hamiltonian dynamics をシミュレートし、特に電子構造の問題を解決するためには、この方法が好まれる方法になりました。

大まかに言えば、qubitization は次の手順に従ってこれを実現します。
1つ目は、$H = \ sum_j h_j H_j、および $H _j $ および $h _j $0 です。
Qubitization は、反射のペアを実行することで、$ $W = e ^ {\ pm i \ cos ^ {-1} (H/| h | _1)}, $ $ where $ | H | _1 = \ sum_j | h_j | $ と等価の演算子を実装します。
次の手順では、ウォーク演算子の固有値を $e ^ {i\ pm \ cos ^ {-1} (E_k/| h | _1)} $ から変換します。ここで $E _k $ は $H $ の固有値 $e ^ {-iE_k t} $ です。
これは、クォンタムの [シグナル処理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)など、さまざまなクォンタムの単数値の変換方法を使用して実現できます。

または、静的な数量のみが必要な場合 (Hamiltonian の接地エネルギーなど)、その結果のコサインを取得することにより、$W $ に直接 [位相推定](xref:microsoft.quantum.libraries.characterization) を適用して、結果からの地表エネルギーを推定することができます。
これは、クォンタムの単数値の変換方法を使用するのではなく、クラシックデプロイによってスペクトル変換を実行できるため、重要です。

より詳細なレベルでは、qubitization の実装には、Hamiltonian のインターフェイスを提供する2つのサブルーチンが必要です。
Trotter – Suzuki メソッドとは異なり、これらのサブルーチンは古典的なクォンタムではなく、実装では、Trotter ベースのシミュレーションに必要とされるよりも大きな対数ビットを使用する必要があります。

Qubitization で使用される最初のクォンタムサブルーチンは $ \ name{select} $ という名前で、\ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \ end{} を生成することが想定されています。ここで、各 $H _j $ は、Hermitian とと想定されています。
これは制限されているように思えるかもしれませんが、PHermitian の演算子は、そのようなものであることを思い出してください。そのため、量子化学シミュレーションなどのアプリケーションは、このフレームワークに自然に分類されます。
$ 演算子は、実際には実際にはリフレクション操作であることがあります。
これは、$ k {j} \ket{\psi} = \ket{j} \ket{\psi} $ という事実から見ることができます。これは、各 $H _j $ がユニタリおよび Hermitian であり、そのために固有値 $ pm $1 があるためです。

2番目のサブルーチンは、$ & によって呼び出されます。
Select 操作では、各 Hamiltonian terms _j $H にアクセスする手段が提供されていますが、prepare サブルーチンでは係数にアクセスするためのメソッドを使用 $h _j $,-begin{} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
次に、乗算制御されたフェーズゲートを使用して、$ $ \Lambda\ket {0} ^ {/otimes n} = \begin{cases} \- \ket{x} & \ text{if} x = 0 と表示されます。 \\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

$ Qubitization を直接使用することはできませんが、$-\begin{align} R &amp; = 1-2 \ オペレーター名 {Prepare} \ket \bra/\ のように作成された状態についてのリフレクションを実装するために使用されています (& a) {Prepare} \ 演算子名 {/ {0} ラムダ/演算子です {0} {-1} \\ \\ &amp; {-1} 。
\end{align} $ $

ウォーク演算子 $W $ は、$ & operator name{select} $ および $R $ operation as $ $ W = \ 演算子 name{select} R, $ $ として表すことができます。これにより、同等の演算子 (アイソメトリック) を実装して、^ {/pm i-cos ^ {-1} (H/| H | _1)} $ を $e できます。

これらのサブルーチンは、で簡単に設定 Q# できます。
例として、$H = X_1 + X_2 + Z_1 Z_2 $ という単純な qubit の横形式の Hamiltonian を考えてみます。
この場合、 Q# $ 演算子を実装するコードはによって呼び出されますが、 <xref:Microsoft.Quantum.Canon.MultiplexOperations> $-演算子はを使用して実装することができ <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> ます。
一例として、このモデルのシミュレーションを含む例[ Q# があります。](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)

任意の化学の問題に対してこれらの手順を手動で指定すると、多くの労力が必要になります。これは、化学ライブラリを使用しても回避できます。
上記の Trotter – Suzuki シミュレーションアルゴリズムと同様に、は、その `JordanWignerEncodingData` `QubitizationOracle` 実行に必要なその他のパラメーターに加えて、ウォーク演算子を返す便利な関数に渡されます。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

重要な実装 <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> は、PHamiltonians li 文字列の線形組み合わせとして指定された任意のに適用されます。
化学シミュレーション用に最適化されたバージョンは、を使用して呼び出され <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> ます。
このバージョンは、「 [量子回線での電子 Spectra のエンコード](https://arxiv.org/abs/1805.03662)」で説明されている手法を使用した t ゲートの数を最小限に抑えるために最適化されています。
