---
title: 2番目の量子化 |Microsoft Docs
description: 2番目の量子化の概念ドキュメント
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210414"
---
# <a name="second-quantization"></a>2番目の量子化

2番目の量子化では、別のレンズによって電子構造の問題を確認します。
2番目の量子化では、各 $N を特定の状態 (または回転) に割り当てるのではなく、各回転を追跡し、それぞれに電子メールがあるかどうかを保存し、同時に、原子の対称プロパティを自動的に保証します。対応する wave 関数。
これは、入力状態の symmetrizing を気にすることなく、量子化学モデルを指定できるようにするために重要です。また、2つ目の量子化により、このようなモデルは小さいクォンタムを使用してシミュレートできます。コンピューター.

2番目の量子化の例として、$ \psi_0\cdots \psi_{N-1} $ は空間 orbitals の orthonormal セットであると仮定します。
これらの方法は、考慮された有限の基準でシステムをできるだけ正確に表すように選択されています。
このような場合の一般的な例としては、hydrogen atom の eigenbasis を形成する atomic orbitals があります。
原子には2つのスピン状態があるため、2つの原子を各空間回転にぎゅうぎゅうできます。
つまり、有効な基礎となる状態は、$ \psi_{0、\uparrow}、\ lドット、\psi_{N-1、\uparrow}、\psi_{0、\ downarrow}、\ lドット、\psi_{N-1、\ downarrow} $ という形式です。ここで、$ \uparrow $ と $ は、スピンレベルの2つの eigenstates を指定するラベルです。幅広い.
$ (J, \ シグマ) $ for \{$ \uparrow\}, 回転の結合インデックスは、空間とスピンの自由度の両方を格納しているため、スピンと呼ばれています。
化学ライブラリでは、スピン orbitals は `SpinOrbital` データ構造に格納され、次のように作成されます。

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

これは、wave 関数のスピンと空間の両方の部分の基礎を $ \psi_{0} \ cドット \psi_{2N-1} $ として正式に考えることができることを意味します。ここでは、各インデックスが $ (j,-シグマ) $ の列挙体になります。
考えられる列挙の1つとして、$g (j,-シグマ) = j + n \ シグマ ' $ があります。
もう1つの考えられる列挙は $h (j, \ シグマ) = 2 * j +-シグマ $ です。
Quantum の化学ライブラリでは、これらの規則を使用できます。このようなエンコーディングでは、スピン orbitals は次のようにインスタンス化できます。

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

Fermionic システムの場合、P# li 除外の原則を使用すると、1つのスピン回転に複数の電子日が同時に存在するのを防ぐことができます。
これは \\、$ \ket $ が使用されていない場合は、$ \psi_1 $ as/begin{\psi_1} \rightarrow \begin{cases} \psi_1{0}_1 & の2つの有効な状態を書き込むことができることを意味し \
$ \psi_1 $ が占有されている場合、\ket{1}_1 & \ text{ \end{cases}、このエンコードは、1つのクォンタムビットとして電子職業を格納できることを意味するため、quantum コンピューターには適しています。

$ 2N $ spin orbitals の職業状態は、同様に $ 2N $ qubits に格納できます。
例として、$N = $2 の場合、{1}{0} の状態 $ $ \ket \ket \ket{1} \ket{0}、$ $

は、剰余が空であるスピン orbitals $1 $ と $2 $ に対応します。
同様に、state $ $ \ket{0} \equiv \ket{0} _{0}/cドット \ket{0}_ {N-1}, $ $

には原子がなく、"vacuum state" と呼ばれています。

2番目の量子化の美しい副作用は、クォンタム状態のアンチ対称性を明示的に追跡する必要がなくなることです。
これは、ここで説明するように、状態のアンチ対称性は、スピン回転の電子職業を作成および破棄する演算子の交換規則によって、それ自体を表します。

## <a name="fermionic-operators"></a>Fermionic 演算子

2番目の量子化ベクトルに作用する2つの基本的な演算子を、作成演算子と annihilation 演算子と呼びます。
これらの演算子は、特定の場所で原子を挿入または破棄します。
これらは、それぞれ ^ & dagger_ $ と $a j $ $a 示されています。

たとえば、\begin{align} a ^ & dagger_1 \ket{0}_1 = \ket{1}_1, \ quad a ^ & dagger_1 \ket{1}_1 = 0, \ quad a_1 \ket{0}_1 = 0, \ quad a_1 \ket{1}_1 = \ket{0}_1.
\end{align} ここでは、^ & dagger_1 \ket{1}_1 = 0 $ および $a _1 \ket{0}_1 $ が0ベクトルではなく $ \ket{0}_1 $ を生成する $a に注意してください。
そのため、このような演算子は Hermitian もユニタリでもありません。
<xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 型を使用して、一般的な作成演算子と annihilation 演算子を表します。
たとえば、1つの作成演算子は、次のように表されます。

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

また、このような演算子を使用すると、$ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^/dagger_1 a ^ \dagger_2 \ket{0}^ {/otimes 4} を表すことができます。
$ $ この一連の演算子は、上記上の1つのスピンC#回転ケースと同様のコードを使用して、Hamiltonian シミュレーションライブラリ内に構築されます。
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

$K $ があるシステムでは、$a 作成操作の2回目の量子化で、^ \dagger_i $ が $ $ a ^ \dagger_i \ket{n_1、n_2、、0_i、\ lドット、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ lドット、1_i によって指定されています。,、\ n_k}, $ $ と $ $ a ^ \dagger_i \ket{n_1, n_2、1_i、n_k} = 0、$ $ where $S _i = j < i} a ^-dagger_ a_j $ は、1つのパーティクルの状態にあり、インデックス $j < i $ を持つ、対象の合計数を測定しています (& l)。

3番目の演算子は、2番目の量子表現でもよく使用されます。
この演算子は、数値演算子と呼ばれ、n_i = a ^ \dagger_i a_i によって定義されています。
\ end{\begin{align}} この演算子は、指定されたスピン回転の職業をカウントします。これは、n_i \ket{0}_i & = 0 \ nonumber\\\
n_i \ket{1}_i & = \ket{1}_i.
上記の `FermionTerm` 例と同様に、この数値演算子は次のように構成されます。
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

はらみは、fermionic システムで作成または annihilation 演算子を使用した場合には明らかになります。
ラベルの交換では、有効なクォンタムの状態はすべてアンチ対称である必要があります。
これは、$ $ a ^ \dagger_2 a ^ & dagger_1 \ket{0} =-a ^ & dagger_1 a ^ \dagger_2 \ket{0}であることを意味します。
このような演算子は、"commute" と呼ばれ、通常はすべての $i に対して j $ \begin{align} a ^ \dagger_i a ^/daggerj =-(1-\ delta_ a ^ \dagger_i, \ quad a ^ \dagger_i a_j = \ delta_ i, j}-a_j a ^ \dagger_i. を作成しました。) a ^ & # {}
したがって、次の2つの <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> インスタンスは等価でないと見なされます。
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

各作成演算子の commute では、2つ目の量子表現を使用することによって、取り除くのアンチ対称性によって生じる課題が生じることを意味しています。
代わりに、作成演算子の定義で問題を再現します。 

交換の規則を使用すると、一部の `LadderSequence` インスタンスは、実際には同じシーケンスの fermionic 演算子に対応します。これはマイナス記号の場合もあります。
たとえば、Hamiltonian $a (0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 =-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 $) を考えます。
これにより、`FermionTerm`ごとに正規の順序を定義できます。
すべての `FermionTerm` は、次のように自動的に正規の順序で配置されます。
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>2番目-量子化 Fermionic Hamiltonian

[たとえば、電子システムのクォンタムモデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)の Hamiltonian は、作成演算子と annihilation 演算子の観点から記述できます。
特に、$ \ psi\_j $ が、基礎を形成するスピン orbitals の場合、

\ begin{\hat{H} = \ sum\_{pq} h\_{pq} a ^ \ ダガー\_p a\_q +-frac{1}{2}\ sum\_{pqrs} H\_{pqrs} a ^、ダガー\_p a ^、ダガー\_q a\_ra\_s + h\_{\t extrm nuc}, \ label{eq: totalHam} \ end{}。ここで $h\_{\t extrm nuc} $ は核エネルギー (Oppenheimer 近似の定数) で、

\begin{align} h\_{pq} & = \ int\_{-\mathrm{d}}\*\_p (x\_1) \ 左 (-\frac{\nabla ^ 2}{2} + V (x\_1) \ 右) \ psi\_q (x\_1) ^ 3 @no__ を有効にします。t_9_ 1、\end{align}

ここで $V (x) $ は潜在的な平均フィールドです。

\begin{align} h\_{pqrs} & = \ int\_{-x_2\_{-\ inf}} ^ {-\ inf\_p ^\*(x\_1) \ psi\_q ^\*(x\_2) \ 左 (& lt; | {| x_1-|} \right) \ psi\_r (x\_2) \ psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ label {eq: 積分} \end{align}

このようなすべての用語には単一の原子が含まれていますが、同様に $h\_{pqrs} $ は2つの電子積分であるため、{pq} $\_$h という用語は1対1の積分として呼ばれます。
これらの係数の値を計算するには整数が必要であるため、これらは "積分" と呼ばれます。
1つの電子項は、個々の原子の kinetic エネルギーと、nuclei の電気フィールドとの相互作用を示しています。
もう一方の2つの電子積分は、原子間の相互作用を記述します。

これらの用語の意味については、それぞれを構成する作成と annihilation の演算子から得られる直感があります。
たとえば、$h _ {pq} a ^ \dagger_p a_q $ は、スピン回転 $q $ からスピン回転 $p $ までの電子ホッピングについて説明します。
同様に、_ {pqrs} a ^ \dagger_p a ^ & daggera_r a_s $ (distinct $p、q、r、s $) $s と $h いう用語は、スピン orbitals $r $ の2つの原子について記述し、それぞれのに対して、スピン orbitals $p $ と $q $ で終了します。
$R = q $ および $p = s $ の場合 $h _ {prrp} a ^ \dagger_p a ^ \dagger_r a_r a_p = h_ {prrp} n_p n_r $ により、2つの原子に関連付けられたエネルギーペナルティが互いに近接していますが、dynamical プロセスは記述されていません。

`FermionHamiltonian` クラスを使用して、このような Hamiltonians を表す場合があります。これは、基本的に必要なすべての `FermionTerm` インスタンスを含むリストです。
Hamiltonians が Hermitian で定義されているため、用語のインデックスを作成するには、条件が等しいかどうかをチェックするときに Hermitian 対称も使用する、特化された型 `HermitianFermionTerm` を使用します。

いくつかの例を作成してみましょう。
Hamiltonian $ \hat{H} = a_0 ^ \ ダガー a_1 + a_1 ^ \ ダガー a_0 $ を考えてみましょう。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
Hamiltonian 演算子は Hermitian 演算子であるという事実を使用して、この構築を簡略化することがあります。
`Add`を使用して Hamiltonian に用語を追加すると、`fermionTerm0` などの非 Hermitian 用語は、その Hermitian 共役とペアになると見なされます。
したがって、次のスニペットも同じ Hamiltonian を表しています。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

交換の規則を使用すると、Hamiltonian 内の一部の `FermionTerm` インスタンスは、実際には同じシーケンスの fermionic 演算子に対応します。これは、マイナス記号の場合もあります。
たとえば、Hamiltonian $H = a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 = 2a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 $ を考えてみます。これは、上記で構築された用語の合計です。
ユーザーにとっては、これらが同等の条件であるとは限りません。そのため、Hamiltonian に個別に追加される可能性があります。
または、Hamiltonian 内の既存の用語を変更することもできます。
このような場合は、次のように同等の用語を組み合わせることができます。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
同等の用語の係数を組み合わせることにより、Hamiltonian 内の用語の合計数を減らすことができます。
後で、Hamiltonian をシミュレートするために必要なクォンタムゲートの数を減らします。

### <a name="internal-representation"></a>内部表現

1と2つの本文の相互作用を持つ fermionic Hamiltonian は、次のように2番目の量子化表記で表されます。

$ $ \begin{align} H = \ sum\_{pq} h\_{pq} a ^、ダガー\_{p} a\_{q} +-frac{1}{2}\ sum\_{pqrs} H\_{pqrs} a ^ ダガー\_{p} a ^-ダガー\_{q} a\_{r}\_{s}。
\end{align} $ $

この表記法では、最大 $N ^ 2 + N ^ 4 $ 係数があります。
ただし、これらの係数の多くは、同じ演算子に対応するために収集される可能性があります。
たとえば、$p、q、r、s $ が個別のインデックスである場合、交換ルールを使用して、次のように表示されることがあります: $ $ a ^-ダガー\_{p} a ^-ダガー\_{q} a\_{r} a\_{s} ap} a\_{r} a\_{s} =-a ^、ダガー\_{p} a ^/ダガー\_{q} a\_{s} a\_{r} = a ^-ダガー\_{q} a ^、ダガー\_{p} a\_{s} a\_{r}。
$$

さらに、$H $ は Hermitian のように、Hermitian fermionic のすべての非演算子は、\_$h たとえば、\_{p} a ^/ダガー\_{q} a\_{r} a\_{s} $ として、$H $ にも存在する Hermitian 共役を持っています。 これらの symmetries によって特徴付けられた用語のグループに一意にインデックスを付けるために、インデックス $ (i\_1、\ cドット、i\_n、j\_1、\ cドット、j\_m) $ に対して、任意のシーケンスの任意のシーケンスの $n + m $ fermionic 演算子 $a ^ \ ダガー @no__t_4 を指定します。_ {i\_1}/cドット a ^ &\_{i\_n} a\_{j\_1} \ a\_{j\_m} $as 次のようになります。
-   すべての作成演算子 $a ^ \ ダガー\_{i\_\ cdot} $ は、すべての annihilation $a 演算子の前に配置されます ({j\_\ cdot} $)。
-   すべての作成演算子のインデックスは昇順に並べ替えられます。つまり、\_1 < i\_2 < < i\_n $ $i ます。
-   すべての annihilation 演算子インデックスは降順に並べ替えられます。これは\_1 > j\_2 \ ドット > j\_m $ に $j ます。
-   左端のインデックスは右端のインデックスよりも小さいか、または\_1 \ le j\_m $ と $i ます。

この一連の正規インデックスを $ $ \begin{align} として特定します (i\_1、\ cドット、i\_n、j\_1、\ cドット、j\_m)。\_{n, m}。
\end{align} $ $

この正規の順序を使用すると、fermionic Hamiltonian は $ $ \begin{align} H = \ sum\_{(p, q) \ in S\_{1,1}} H '\_{pq} \frac{a ^\_{p} a\_{q} + a ^/ダガー\_{q} a\_{p}}{2}+ \ 合計\_{(p, q, r, s) \\_{2,2}} h '\_{pqrs} \frac{a ^ \ ダガー\_{p} a ^-ダガー\_{q} a\_{r} a\_{s} + a ^ ダガー\_{s} a ^ダガー\_{r} a\_{q} a\_{p}}{2}、\end{align} $ $ は、適切に適用されており、1つと2つの電子的な $h 積分が適用されます。

