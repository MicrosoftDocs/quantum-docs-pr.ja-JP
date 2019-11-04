---
title: 相関 wavefunctions |Microsoft Docs
description: Quantum Dynamics の概念ドキュメント
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 0b14f373d31c5b63e313e07810daf62d9195b1d3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184034"
---
# <a name="correlated-wavefunctions"></a>相関 wavefunctions

多くのシステム (特に均衡ジオメトリの近くにある) では、 [Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock)理論では、単一決定の参照状態を通じて分子プロパティの定性的な説明が提供されます。 ただし、定量的精度を実現するには、相関関係の影響も考慮する必要があります。 

このコンテキストでは、動的と非動的の相関関係を dinstinguish することが重要です。
Dynamical の相関関係は、原子のような傾向があるとしても、電子的な斥力のようなものではありません。 この効果は、参照状態の原子の excitations を考慮することによって、モデル化にすることができます。 非動的な相関関係は、wavefunction が取り出しの順序で2つ以上の構成によって支配されている場合に発生します。これは、システムの定性的な説明だけを達成する場合でも同様です。
これには、要因の法則があり、multireference wavefunction の例があります。

化学ライブラリを使用すると、法則の要因として、multireference の問題に取り出し order wavefunction を指定することができます。 この方法は、スパース multireference wavefunctions と呼ばれ、法則を指定するのに十分な数のコンポーネントだけがある場合に有効です。 また、このライブラリには、汎用化されたユニタリ (クラスター ansatz) を使用した単一の決定参照の上に動的な相関関係を含めるメソッドも用意されています。 さらに、クォンタムコンピューターでこれらの状態を生成するクォンタム回線も構築されます。 これらの状態は[Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)で指定できます。また、化学ライブラリを使用してこれらの状態を手動で指定する機能も用意されています。

## <a name="sparse-multi-reference-wavefunction"></a>スパースマルチ参照 wavefunction
複数参照の状態 $ \ket{\psi_{\rm {MCSCF}}} $ は、$-電子を後で決定する $N の線形の組み合わせとして明示的に指定できます。
\begin{align} \ket{\psi_{\rm {MCSCF}} <}{0}i_N i_2 \lambda_{i_1、i_2、\ cドット、i_N} a ^ & dagger< < a ^ \dagger_{i_N}\ket ですが、していないことを確認してください (& a)。、、、、および。
\end{align} たとえば、次のように、州 $ \ propto (0.1 a ^ & dagger\ket >-dagger/0.2 a ^ & dagger){0}$ を化学ライブラリに指定することができます (& d)。この例を次に示します。
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
法則コンポーネントのこの明示的な表現は、いくつかのコンポーネントのみを指定する必要がある場合に有効です。 望ましい状態を正確にキャプチャするために多くのコンポーネントが必要な場合は、この表現を使用しないようにする必要があります。 この理由は、クォンタムコンピューターでこの状態を準備するクォンタム回線のゲートコストであり、少なくとも法則コンポーネントの数を使用して線形的にスケーリングし、法則の quadratically の1つの値で最大をスケールします。

## <a name="unitary-coupled-cluster-wavefunction"></a>イン wavefunction クラスターの組み合わせ
Chemistery ライブラリを使用して、wavefunction $ \ket{\psi_{\rm {UCC}} $ という組み合わせを指定することもできます。 このような状況では、"$ \ket{\psi_{\rm{SCF}}} $" という1つの決定の参照状態があります。 次に、参照状態に作用するユニタリ演算子を使用して、implicity の wavefunction の構成要素を指定します。
このユニタリ演算子は、通常、$e ^ {T-T ^-dagger} $ として記述されます。ここで $T-T ^ \ ダガー $ は、Hermitian クラスター演算子です。 したがって、\begin{align} \ket{\psi_{\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\psi_{\rm{SCF}}}.
\end{align}

また、クラスター演算子 $T = T_1 + T_2 + \ cドット $ を部分に分割することも一般的です。ここでは、各 $T 部分に $j $ body という用語が含まれています。 一般化された結合クラスター理論では、1つの本体のクラスター演算子 (単一) は、\begin{align} T_1 = という形式になっています。 T ^ {p} _ {q} a ^ \dagger_p a_q, \end{align}

また、2つのボディを持つクラスター演算子 (double) は、\begin{align} T_2 =-sum} _ {rs} a ^ \dagger_p a ^ & daggera_r a_s という形式です。
\end{align}

高順序の用語 (3 要素、となど) は可能ですが、現在は化学ライブラリではサポートされていません。

たとえば、let $ \ket{\psi_{\rm{SCF}}} = a ^ & dagger_1 a ^ \dagger_2\ket{0}$、let $T = 0.123 a ^ a_1 + 0.456 a ^-dagger + a ^ a_1 a_2-0.789 a ^ dagger/3a ^ \dagger_2 a_1 a_0 $ のようにします。 この状態は、次のように化学ライブラリでインスタンス化されます。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

代わりに、整数のインデックスではなく `SpinOrbital` のインデックスを指定することによって、スピン convervation を明示的にすることができます。 たとえば、let $ \ket{\psi_{\rm{SCF}}} = a ^ & d。 \uparrow} a ^ \uparrow} \downarrow}\ket{0}$、let $T = 0.123 a ^ & dagger、a_ {1、\uparrow} + 0.456 a ^-dagger、\uparrow} a ^-a_ {1, \uparrow} a_ {2, \ のようにして使用することができます。downarrow}-0.789 a ^ \uparrow}, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ be spin convserving. ($ {1, {0, $ be spin) この状態は、次のように化学ライブラリでインスタンス化されます。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

また、会話クラスターのすべての操作を列挙する便利な関数も用意されています。この関数では、annihilate のみが使用されています。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```