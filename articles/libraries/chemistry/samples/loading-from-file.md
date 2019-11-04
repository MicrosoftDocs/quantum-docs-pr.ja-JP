---
title: ファイルから Hamiltonian を読み込んでいます |Microsoft Docs
description: ファイルからの Hamiltonian の読み込みに関するドキュメント
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 9902e95b09d38323b4b91c29ab897a4f0124b6cd
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184187"
---
## <a name="loading-a-hamiltonian-from-file"></a>ファイルからの Hamiltonian の読み込み
以前は、個別の用語を追加して Hamiltonians を構築していました。 これは、小さな例では問題ありませんが、大規模な量子化学には、何百万または十億の Hamiltonians が必要です。 NWChem などの化学パッケージによって生成された Hamiltonians は、大きすぎて手動でインポートすることができません。 このサンプルでは、 [Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)によって表される分子から、`FermionHamiltonian` インスタンスが自動的に生成される方法を説明します。 参考のために、提供されている `LithiumHydrideGUI` サンプルまたは `RunSimulation` サンプルを調べることができます。 [LIQUi | >](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)で使用される形式からのインポートについても、制限付きサポートを利用できます。

サンプルリポジトリの `IntegralData/YAML` フォルダーに用意されている Nitrogen 分子の例を考えてみましょう。 `Broombridge` スキームの読み込み方法は簡単です。

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

Broombridge スキーマには、準備する初期状態の提案も含まれています。 これらの状態のラベル (`"|G⟩"`、`"|E1⟩"`など) は、ファイルを調べることで確認できます。 これらの初期状態を準備するために、Q # クォンタムアルゴリズムによって使用される `qSharpData` は[前のセクション](xref:microsoft.quantum.chemistry.examples.energyestimate)と同様に取得されますが、必要な初期状態を選択するパラメーターが追加されています。 たとえば、
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

非常によく似た構文を使用して、LIQUi | > 形式から Hamiltonian を読み込むこともできます。 

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