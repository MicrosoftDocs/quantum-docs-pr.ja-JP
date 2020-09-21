---
title: 2番目の量子化
description: クォンタムプログラミングで電子構造をモデル化するための2番目の量子化アプローチについて説明します。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835810"
---
# <a name="second-quantization"></a>2番目の量子化

2番目の量子化では、別のレンズによって電子構造の問題を確認します。
各 $N _e $ 原子を特定の状態 (または回転) に割り当てるのではなく、2番目の量子化で各回転を追跡し、各に電子が存在するかどうかを保存し、同時に、対応する wave 関数の対称プロパティを自動的に確保します。
これは、入力状態の symmetrizing を気にすることなく、量子化学モデルを指定できるようにするために重要です。また、2つ目の量子化では、小さなクォンタムコンピューターを使用してこのようなモデルをシミュレートできます。

2番目の量子化の例として、$ \ psi_0/cドット \ psi_ {N-1} $ が空間 orbitals の orthonormal セットであるとします。
これらの方法は、考慮された有限の基準でシステムをできるだけ正確に表すように選択されています。
このような場合の一般的な例としては、hydrogen atom の eigenbasis を形成する atomic orbitals があります。
原子には2つのスピン状態があるため、2つの原子を各空間回転にぎゅうぎゅうできます。
つまり、有効なベースの状態は $ \ psi_ {0 の形式になります。 \uparrow}、\uparrow}、\ psi_ {N-1、、\ psi_ {0, \ downarrow}, \ lドット, \ psi_ {N-1, \ downarrow} $ ここで、$ \uparrow $ と $ $ は、スピンの自由度の2つの eigenstates を指定するラベルです。
$ (J,-シグマ) $ for $ \uparrow, 回転のこの結合インデックス \{ \} は、空間とスピンの自由度の両方を格納するため、スピンと呼ばれます。
化学ライブラリでは、スピン orbitals はデータ構造に格納され、次のように作成され `SpinOrbital` ます。

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

これは、wave 関数のスピンと空間の両方の部分を、$ \ psi_ \ ドット \ psi_ {2N-1} $ として正式に考えることができることを意味し {0} ます。ここでは、各インデックスが $ (j,-シグマ) $ の列挙体です。
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
つまり、$ \ psi_1 $ as \ begin{\begin{cases}} \ psi_1 \rightarrow \ket {0} _1 &-$ \ psi_1 $ が使用されていない場合、この2つの有効な状態を書き込むことができます。 \\\
{1}$ \ psi_1 $ が占有されている場合、\ket _1 & \ text{ \end{cases}、このエンコードは、1つのクォンタムビットとして電子職業を格納できることを意味するため、quantum コンピューターには適しています。

$ 2N $ spin orbitals の職業状態は、同様に $ 2N $ qubits に格納できます。
例として、$N = $2 の場合は、$ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $ という状態になります。

は、剰余が空であるスピン orbitals $1 $ と $2 $ に対応します。
同様に、state $ $ \ket {0} \equiv \ket {0} _ {0} \ cドット \ket {0} _{N-1}, $ $

には原子がなく、"vacuum state" と呼ばれています。

2番目の量子化の美しい副作用は、クォンタム状態のアンチ対称性を明示的に追跡する必要がなくなることです。
これは、ここで説明するように、状態のアンチ対称性は、スピン回転の電子職業を作成および破棄する演算子の交換規則によって、それ自体を表します。

## <a name="fermionic-operators"></a>Fermionic 演算子

2番目の量子化ベクトルに作用する2つの基本的な演算子を、作成演算子と annihilation 演算子と呼びます。
これらの演算子は、特定の場所で原子を挿入または破棄します。
これらは、それぞれ ^ \ dagger_j $ と $a _j $ $a 示されています。

たとえば、\begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \ クワッド a ^ \ dagger_1 \ket {1} _1 = 0, \ クワッド a_1 \ket _1 = {0} 0, \ quad a_1 \ket {1} _1 = \ket {0} _1.
\end{align} ここでは、^ dagger_1 \ket {1} _1 = 0 $、$a _1 \ket {0} _1 $ を $a、0ベクトルではなく $ \ket _1 $ を生成することに注意して {0} ください。
そのため、このような演算子は Hermitian もユニタリでもありません。
型を使用して、一般的な作成演算子と annihilation 演算子を表し <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> ます。
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

また、このような演算子を使用すると、$ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ dagger_2 \ket {0} ^ {/otimes 4} を表すことができます。
$ $ この一連の演算子は、前述の単一スピン回転ケースと同様の C# コードを使用して、Hamiltonian シミュレーションライブラリ内に構築されます。
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

$K $ があるシステムの場合、2番目の量子化では、作成演算子 $a ^ \ dagger_i $ が $ $ a ^ \ dagger_i \ket{n_1、n_2、\ lドット、0_i、\ lドット、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ lドット、1_i、\ lドット、n_k}、$ $ および $ $ a ^ dagger_i \ket{n_1、n_2、\ lドット、1_i、\ l点線、n_k} = 0、$ $ where $S _i = \ sum_ {j<i} a ^ dagger_j a_j $ は、1つのパーティクルの状態にあり、インデックス $j i $ を持つ、すべての対象の合計数を測定します。

3番目の演算子は、2番目の量子表現でもよく使用されます。
この演算子は、数値演算子として知られています。また、この演算子は、& lt; n_i = a ^ \ dagger_i a_i で定義されています。
\ end{\begin{align}} この演算子は、指定されたスピン回転の職業をカウントします。これは、n_i {0} _i \ket &= 0 \ nonumber になります。\\\
n_i \ket {1} _i &= \ket {1} _i。
\end{align} の例と同様に `FermionTerm` 、この数値演算子は次のように構成されます。
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
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
つまり、$ $ a ^ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} です。
$ $ このような演算子は ' commute ' $i と呼ばれます。 j $ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i、\ quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i です。
したがって、次の2つの <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> インスタンスは等価でないと見なされます。 \end{align}
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

交換の規則を使用すると、一部のインスタンスが実際には `LadderSequence` 同じシーケンスの fermionic 演算子に対応し、場合によってはマイナス記号が適用されます。
たとえば、Hamiltonian $a 0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 =-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 $ とします。
これにより、すべてのに対して標準の順序を定義するため `FermionTerm` ます。
次のよう `FermionTerm` に、が自動的に正規の順序で配置されます。
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
特に、$ \ psi \_ j $ が、基礎を形成するスピン orbitals の場合、

\ begin{nuc} \hat{H} = \ sum \_ {pq} h \_ {pq} a ^ \_ -ダガー p a \_ q +-frac {1} {2} -sum \_ {pqrs} H \_ {pqrs} a ^-ダガー \_ p a ^ \ ダガー \_ q a \_ ra \_ s + h \_ {\t extrm}, \ label{eq: totalHam} \ end{}。ここで $h \_ {\t extrm nuc} $ は核エネルギー (Oppenheimer 近似の定数) で、

\begin{align} h \_ {pq} &= \ int \_ {-\ inf}} ^ \ inf\ psi ^ \* \_ p (x \_ 1) \ left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \ right) \ psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}

ここで $V (x) $ は潜在的な平均フィールドです。

\begin{align} h \_ {pqrs} &= \ int \_ {---{-\ inf} ^ \ inf\ int \_ {-\ (& a) {-/inf} ^ \_ \* (x \_ 1) \ psi \_ q ^ \* (x \_ 2) \ 左 (\ frac {1} {| x_1-x_2 |} \ 右) \ psi \_ r (x \_ 2) \ psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ label {eq: 積分} \end{align}

$H {pq} $ という用語は1つの \_ 原子と呼ばれています。これは、このようなすべての用語には単一のが関係していて、同様に $h \_ {pqrs} $ が2つの電子積分であるためです。
これらの係数の値を計算するには整数が必要であるため、これらは "積分" と呼ばれます。
1つの電子項は、個々の原子の kinetic エネルギーと、nuclei の電気フィールドとの相互作用を示しています。
もう一方の2つの電子積分は、原子間の相互作用を記述します。

これらの用語の意味については、それぞれを構成する作成と annihilation の演算子から得られる直感があります。
たとえば $h _ {pq} a ^ dagger_p a_q $ は、スピン回転 $q $ からスピン回転 $p $ までの電子ホッピングを記述します。
同様に、_ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (distinct $p、q、r、s $) では、原子2つのがスピン orbitals $r $ に記述さ $h れています。また、これらは、それぞれがスピン orbitals $s $ と $p $ で終了します。
$R = q $ および $p = s $ に $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ によって、互いに近くにある2つの原子に関連するエネルギーペナルティが与えられますが、dynamical プロセスについては説明しません。

クラスを使用して、このような Hamiltonians を表す場合があり `FermionHamiltonian` ます。これは、基本的に、すべての目的のインスタンスを含むリストです `FermionTerm` 。
Hamiltonians が Hermitian によって定義されているため、用語 `HermitianFermionTerm` が等しいかどうかをチェックするときに Hermitian 対称も使用する、より特殊な型を使用して用語にインデックスを付けます。

いくつかの例を作成してみましょう。
Hamiltonian $ \hat{H} = a_0 ^ a_1 + a_1 ^ \ ダガー a_0 $ を考えてみます。
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
を使用して Hamiltonian に用語を追加する場合 `Add` 、などの Hermitian 以外の用語 `fermionTerm0` は、その Hermitian 共役とペアリングされていると見なされます。
したがって、次のスニペットも同じ Hamiltonian を表しています。
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

交換規則を使用すると、Hamiltonian の一部のインスタンスは、実際には `FermionTerm` 同じシーケンスの fermionic 演算子に対応します。これは、マイナス記号の場合もあります。
たとえば、Hamiltonian $H = a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0-a_1 ^ \ ダガー a_0 ^ \ ダガー a_1 a_0 = 2a_0 ^ \ ダガー a_1 ^ \ ダガー a_1 a_0 $ (上記で構築した用語の合計) について考えてみます。
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

$ $ \begin{align} H = \ sum \_ {pq} H \_ {pq} a ^-ダガー \_ {p} a \_ {q} +-frac/ {1} {2} sum \_ {pqrs} H \_ {pqrs} a ^-ダガー \_ {p} a ^-ダガー \_ {q} a \_ {r} a \_ {s}。
\end{align} $ $

この表記法では、最大 $N ^ 2 + N ^ 4 $ 係数があります。
ただし、これらの係数の多くは、同じ演算子に対応するために収集される可能性があります。
たとえば、$p、q、r の場合、s $ は個別のインデックスであり、交換ルールを使用して、そのことを示す場合があります: $ $ a ^ ダガー \_ {p} a ^ ダガー \_ {q} a \_ {r} a { \_ s} =-a ^ \ ダガー \_ {q} a ^-ダガー { \_ p} a \_ {r} a \_ {s} =-a ^ \ ダガー \_ {p} a ^-ダガー \_ {q} a \_ {s} a \_ {r} = a ^-ダガー \_ {q} a ^ ダガー \_ {p} a { \_ s} a \_ {r}。
$$

さらに、$H $ が Hermitian の場合、Hermitian fermionic のすべての非演算子 ($h たとえば、 \_ {pqrs} a ^ \ ダガー { \_ p} a ^ \ ダガー \_ {q} a \_ {r} a \_ {s} $ には、$H $ にもある Hermitian 共役があります。 これらの symmetries によって特徴付けられる用語のグループに一意にインデックスを付けるために、 \_ \_ \_ \_ 任意のシーケンスの $n + m $ fermionic operators のインデックス $ (i 1、\ cドット、i n、j 1、\ cドット $as $a、j m) $ \_ に \_ \_ \_ \_ \_ \_ 正規の \_ 順序を定義しています。これには、次のように、任意のシーケンスの任意のシーケンスを指定します。
-   すべての作成演算子 $a ^ \ ダガー \_ {i \_ \ cdot} $ は、すべての annihilation 演算子 $a \_ {j \_ \ dot} $ の前に配置されます。
-   すべての作成演算子のインデックスは昇順に並べ替えられます \_ 。つまり $i 1< i \_ 2</cドット < i \_ n $ になります。
-   すべての annihilation 演算子インデックスは降順に並べ替えられ、 \_ 1> j \_ 2、cドット > j \_ m $ $j ます。
-   左端のインデックスは、右端のインデックスの値以下で、$i \_ 1 \ le j \_ m $ です。

この一連の正規の順序付けされたインデックスを $ $ \begin{align} (i \_ 1、\ cドット、i \_ n、j \_ 1、\ cドット、j m) として \_ \_ 、{n, m} で特定します。
\end{align} $ $

この標準の順序を使用すると、fermionic Hamiltonian は $ $ \begin{align} H = \ sum \_ {(p, q) \ sum {(p, q) \ In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \_ /ダガー {p} a { \_ q} + a ^-ダガー { \_ q} a \_ {p}} {2} + \ sum \_ {(p, q, r, s) \ in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \ ダガー \_ {p} a ^-ダガー { \_ q} a \_ {r} a \_ {S} + a ^-ダガー \_ {s} a ^ ダガー \_ {r} a { \_ q} a \_ {p}} {2} 、\end{align} $ $ は、適切に調整された1つの積分と2つの $h の $h を ' \_ {pq} $ と ' \_ {pqrs} $ ' としています。

