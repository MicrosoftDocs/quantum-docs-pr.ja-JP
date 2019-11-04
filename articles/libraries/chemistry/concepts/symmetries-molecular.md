---
title: Symmetries 分子積分 |Microsoft Docs
description: 分子の Symmetries の概念に関するドキュメント
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442384"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries 分子の積分

クーロン Hamiltonian の本質的な対称性は、[電子システムの Quantum モデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)で指定された Hamiltonian であり、相互にやり取りする原子と nuclei について説明しています。これは、Hamiltonian の用語を圧縮するために悪用されます。
一般に、基本関数 $ \psi_j $ に関してこれ以上の仮定が行われていない場合は、次のようにします。これは、[のクォンタムモデルの積分からすぐにわかるように、h_ {pqrs} = h_ {qpsr}、\ tag{★} です。](xref:microsoft.quantum.chemistry.concepts.quantummodels)$P、q $ および $r、s $ が交換と交換された場合、その値は同じままです。

スピン orbitals が実際の値であると想定した場合 (ガウス回転ベースの場合)、h_ {pqrs} = h_ {qpsr} が追加されます。 = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {spqr} = h_ {qrsp} .\tag {★} \ label{eq: hpqrsreal} \ end{式} このような仮定がある場合は、上記の symmetries を使用して、Hamiltonian のマトリックス要素を格納するために必要なデータを $8 $ の係数で減らすことができます。ただし、これにより、一貫性のある方法でデータを簡単にインポートできるようになります。
幸いなことに、Hamiltonian シミュレーションライブラリには、 [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)から、または[nwchem](http://www.nwchem-sw.org/index.php/Main_Page)から直接、整数ファイルをインポートするために使用できるサブルーチンがあります。

分子回転の積分 ($h\_{pq} $ と $h\_{pqrs} $ terms) は、この対称を表現するために役立つ多くの関数を提供する `OrbitalIntegral` 型を使用して表されます。
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

数値が同じであるすべての回転積分を列挙するだけでなく、`OrbitalIntegral` によって表される Hamiltonian に含まれるすべての回転インデックスの一覧が次のように生成される場合があります。
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>分子積分からの Fermionic Hamiltonians の構築

`FermionTerm`s を追加して Fermionic Hamiltonian を構築するのではなく、各回転整数に対応するすべての用語を自動的に追加することができます。
たとえば、次のコードは、すべての permutational symmetries を自動的に列挙し、正規の順序で用語を並べ替えます。 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
