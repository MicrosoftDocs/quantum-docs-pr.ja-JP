---
title: Hamiltonian Dynamics をシミュレートする |Microsoft Docs
description: Hamiltonian Dynamics の概念説明ドキュメントをシミュレートする
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864459"
---
# <a name="simulating-hamiltonian-dynamics"></a>Hamiltonian Dynamics のシミュレーション

Hamiltonian が基本演算子の合計として表現されたら、既知の手法のホストを使用して、dynamics を基本的なゲート操作にコンパイルできます。
Trotter – Suzuki 数式、unitaries の線形組み合わせ、qubitization という3つの効果的なアプローチがあります。
以下の3つのアプローチについて説明し、Hamiltonian シミュレーションライブラリを使用してこれらのメソッドを実装する方法の具体的な Q&a 例を示します。


## <a name="trottersuzuki-formulas"></a>Trotter – Suzuki 数式
Trotter – Suzuki 数式の背後にあるアイデアは単純なものです。 Hamiltonian を簡単にシミュレートできる Hamiltonians の合計として表現し、その後、これらの単純な evolutions のシーケンスとして、全体的な進化を概算します。
特に、$H = \ sum_ {j = 1} ^ m H_j $ を Hamiltonian にします。
次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $1 $t $。この近似値のエラーはごくわずかになります。
$E ^ {-i H} $ が通常の指数の場合、この近似値のエラーは $O されません (m ^ 2 t ^ 2) $: 0 になります。
このエラーは $e ^ {-iHt} $ が演算子指数であるために発生します。結果として、この数式を使用すると、$ terms _j $H (*つまり*、$H _j H_k \n e H_k H_j $ general) ではないことが原因でエラーが発生します。

$T $ が大きい場合でも、Trotter – Suzuki 式を使用して、短時間の一連の手順に分割することで、dynamics を正確にシミュレートできます。
$R $ は、時間の進化にかかったステップの数になります。
次に、$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r)、$ $ は、$ $m t ^ 2/\ イプシロン $ として $r $ のスケールを設定した場合、$-イプシロン > 0 $ に対して最大 $/イプシロン $ にエラーを加えることを意味します。

エラー条件がキャンセルされるように、一連の演算子指数を構築することで、より正確な概数を作成できます。
このような式の中で最も単純なのは、$ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3) です。 $ $ イプシロン > 0 $ の $-イプシロン $ より小さくすることができます。 $ {3/2} t ^ {3/2}//sqrt {\ イプシロン} $ としてスケールするには $r $ を選択します。 $m

$U _1 $ に基づいて上位の Trotter 数式を構築することもできます。
最も単純なのは、次の4番目の注文式です。もともと Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5t ^ 5)、$ $ where $s _1 = (4-4 ^ {1/3}) ^{-1}$。
一般に、任意の上位の数式を同様に構築できます。ただし、多くの場合、より複雑なインテグレーターを使用することによって生じるコストは、最も現実的な問題の4番目の順序を超える利点を上回ることになります。

上記の戦略を機能させるためには、$e ^ {-iH_j t} $ の幅広いクラスをシミュレートするためのメソッドが必要です。
ここで使用できる最も単純な Hamiltonians のファミリは、Pare Li 演算子です。
Diagonalized 演算子は、Clifford 操作 (クォンタムコンピューティングの標準ゲート) を使用して実行できるため、簡単にシミュレートできます。
さらに、これらの値が diagonalized されると、それらが作用する qubits のパリティを計算することで、それらの値を見つけることができます。

たとえば、$ $ e ^ {-Ix\ otimes X t} = (hotimes H) e ^ {-Iz\ otimes Z t} (hotimes H), $ $ where $ $ e ^ {-i Z/otimes Z t} = \begin{bmatrix} e ^ {-it &} は 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ ここ、$e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ and $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$。これは、$0 $ のパリティが $0 $ で、ビット文字列 $1 $ のパリティは $1 $ であるという事実の結果として直接確認できます。

指数操作を使用して <xref:microsoft.quantum.primitive.exp>、Q # に直接実装できる p Li 演算子は次のとおりです。
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Fermionic Hamiltonians の場合、[ヨルダン– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)は、Hamiltonian を p li 演算子の合計に簡単にマップします。
これは、化学をシミュレートするために、上記のアプローチを簡単に調整できることを意味します。
次に、このようなシミュレーションを化学内で実行する方法の例を、以下に示します。この例では、このようなシミュレーションを実行する方法を簡単に説明します。
開始点は、コードで `JordanWignerEncoding` クラスのインスタンスとして表現された、Fermionic Hamiltonian の[ヨルダンの Wigner エンコード](xref:microsoft.quantum.chemistry.concepts.jordanwigner)です。

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

この形式では、Q # のシミュレーションアルゴリズムで利用できるヨルダンの形式は、ユーザー定義型 `JordanWignerEncodingData`です。
Q # では、この形式は便利な `TrotterStepOracle` 関数に渡されます。これは、Trotter-Suzuki インテグレーターを使用して、その実行に必要なその他のパラメーターに加えて、時間の短縮度を表す演算子を返します。

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

重要なのは、この実装では、[クォンタムコンピューターを使用した電子構造 Hamiltonians のシミュレーション](https://arxiv.org/abs/1001.3855)で説明されているいくつかの最適化を適用し、必要なシングル qubit 回転数を最小限に抑えるためにクォンタム[化学のクォンタムアルゴリズムを改善](https://arxiv.org/abs/1403.1539)し、シミュレーションエラーを減らします。

## <a name="qubitization"></a>Qubitization

Qubitization は、クォンタムウォークからのアイデアを使用して量子力学をシミュレートする、シミュレーションの代替アプローチです。
Qubitization は Trotter 数式よりも多くの qubits を必要としますが、メソッドは、進化時間と誤差許容範囲に応じて最適なスケーリングを保証します。
このような理由から、一般的な Hamiltonian dynamics をシミュレートし、特に電子構造の問題を解決するためには、この方法が好まれる方法になりました。

大まかに言えば、qubitization は次の手順に従ってこれを実現します。
1つ目は、$H = \ sum_j h_j H_j、および $H _j $ および $h _j $0 です。
Qubitization は、1対の反射を実行することで、$ $W = e ^ {\ pm i \ cos ^{-1}(H/| h | _1)}、$ $ where $ | H | _1 = \ sum_j | h_j | $ と同等の演算子を実装します。
次の手順では、ウォーク演算子の固有値を $e ^ {i\ pm \ cos ^{-1}(E_k/| h | _1)} $ から変換します。ここで $E _k $ は $H $ の固有値 $e ^ {-iE_k t} $ です。
これは、クォンタムの[シグナル処理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)など、さまざまなクォンタムの単数値の変換方法を使用して実現できます。

または、静的な数量のみが必要な場合 (Hamiltonian の接地エネルギーなど)、その結果のコサインを取得することにより、$W $ に直接[位相推定](xref:microsoft.quantum.libraries.characterization)を適用して、結果からの地表エネルギーを推定することができます。
これは、クォンタムの単数値の変換方法を使用するのではなく、クラシックデプロイによってスペクトル変換を実行できるため、重要です。

より詳細なレベルでは、qubitization の実装には、Hamiltonian のインターフェイスを提供する2つのサブルーチンが必要です。
Trotter – Suzuki メソッドとは異なり、これらのサブルーチンは古典的なクォンタムではなく、実装では、Trotter ベースのシミュレーションに必要とされるよりも大きな対数ビットを使用する必要があります。

Qubitization で使用される最初のクォンタムサブルーチンは $ \ 演算子 name{select} $ という名前で、\ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \ end{} を生成することが想定されています。ここで、各 $H _j $ は Hermitian と想定されています。およびユニタリ。
これは制限されているように思えるかもしれませんが、PHermitian の演算子は、そのようなものであることを思い出してください。そのため、量子化学シミュレーションなどのアプリケーションは、このフレームワークに自然に分類されます。
$ 演算子は、実際には実際にはリフレクション操作であることがあります。
これは、$ k {j} \ket{\psi} = \ket{j} \ket{\psi} $ という事実から見ることができます。これは、各 $H _j $ がユニタリおよび Hermitian であり、そのために固有値 $ pm $1 があるためです。

2番目のサブルーチンは、$ & によって呼び出されます。
Select 操作では、各 Hamiltonian terms _j $H にアクセスする手段が提供されていますが、prepare サブルーチンでは $h 係数にアクセスするためのメソッドが用意されています。 _j $,-begin{} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
次に、乗算制御されたフェーズゲートを使用することによって、$ $ \Lambda\ket{0}^ {/otimes n} = \begin{cases} \-\ket{x} &、} x = 0 \\があることがわかります \
        \ket{x} & \text{otherwise} \end{cases}.
$$

$ & Qubitization} $ 操作は、直接には使用されません。しかし、$-\begin{align} R &amp; = 1-2 \ 演算子名 {Prepare} \ket{0}\bra{0}、\\\\ = \ オペレーター名 {} ^ &amp; を作成する状態{-1} に関するリフレクションを実装するために使用されますが、このような場合はを使用します。
\end{align} $ $

ウォーク演算子 $W $ は、$ & operator name{select} $ および $R $ operation as $ $ W = \ operator name{select} R, $ $ として表すことができます。これにより、同じ (アイソメトリック) と $e 同等の演算子を実装することができます。これは、^ {/pm i-cos ^{-1}(H/| H | _1)

これらのサブルーチンは、Q # で簡単に設定できます。
例として、$H = X_1 + X_2 + Z_1 Z_2 $ という単純な qubit の横形式の Hamiltonian を考えてみます。
この場合、$ 演算子を実装する Q # コードは <xref:microsoft.quantum.canon.multiplexoperations>によって呼び出されます。一方、$-演算子名は、<xref:microsoft.quantum.preparation.preparearbitrarystate>を使用して実装できます。
このモデルをシミュレートする例については、 [Q # のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)を参照してください。

任意の化学の問題に対してこれらの手順を手動で指定すると、多くの労力が必要になります。これは、化学ライブラリを使用しても回避できます。
上記の Trotter – Suzuki シミュレーションアルゴリズムと同様に、`JordanWignerEncodingData` は、実行に必要なその他のパラメーターに加えて、ウォーク演算子を返す便利な関数 `QubitizationOracle` に渡されます。

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

重要なの実装 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> は、PHamiltonians Li 文字列の線形組み合わせとして指定された任意のに適用されます。
化学シミュレーション用に最適化されたバージョンは <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>を使用して呼び出されます。
このバージョンは、「[量子回線での電子 Spectra のエンコード](https://arxiv.org/abs/1805.03662)」で説明されている手法を使用した t ゲートの数を最小限に抑えるために最適化されています。
