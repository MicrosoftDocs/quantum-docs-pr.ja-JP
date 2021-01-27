---
title: ファイルからのハミルトニアンの読み込み
description: Broombridge スキーマを使用して大規模な Hamiltonian を自動的に生成する方法について説明します。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4bd663ade7649be05058f07bee1acf541ec3e487
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844118"
---
# <a name="loading-a-hamiltonian-from-file"></a>ファイルからのハミルトニアンの読み込み
以前は、個別の用語を追加して Hamiltonians を構築していました。 これは、小さな例では問題ありませんが、大規模な量子化学には、何百万または十億の Hamiltonians が必要です。 NWChem などの化学パッケージによって生成された Hamiltonians は、大きすぎて手動でインポートすることができません。 このサンプルでは、 `FermionHamiltonian` [Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)によって表される分子からインスタンスが自動的に生成される方法を説明します。 参考までに、提供されている `LithiumHydrideGUI` サンプルまたはサンプルを調べることができ `RunSimulation` ます。 [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)で使用される形式からのインポートについても、制限付きサポートを利用できます。

サンプルリポジトリのフォルダーに用意されている Nitrogen 分子の例を考えてみましょう `IntegralData/YAML` 。 スキーマを読み込むためのメソッド `Broombridge` は簡単です。

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Broombridge スキーマには、準備する初期状態の提案も含まれています。 `"|G⟩"`これらの状態のラベル (例: または `"|E1⟩"` ) は、ファイルを調べることで確認できます。 これらの初期状態を準備するために、 `qSharpData` クォンタムアルゴリズムによって使用 Q# されるは [前のセクション](xref:microsoft.quantum.chemistry.examples.energyestimate)と同様に取得されますが、必要な初期状態を選択するパラメーターが追加されています。 たとえば、
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

次のような便利な方法を使用して、上記の手順をすべて省略できます。
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

また、LIQUi | から Hamiltonian を読み込むこともできます。> 形式。非常によく似た構文を使用します。 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Broombridge の任意のインスタンスまたは中間手順に従ってこのプロセスを実行すると、指定された電子構造の問題に対してクォンタムフェーズの推定などのクォンタムアルゴリズムが実行される可能性があります。
