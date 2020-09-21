---
title: Symmetries 分子の積分
description: Orbitalintegral 型を使用して分子 symmetries を列挙する方法について説明し Q# ます。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ebb8e9bda06967d3cfa002a7d074933d9135ada
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833817"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries 分子の積分

クーロン Hamiltonian の固有の対称性は、 [電子システムの Quantum モデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)で指定された Hamiltonian であり、相互にやり取りする原子と nuclei について説明しています。これにより、symmetries 内の用語を圧縮するために利用できる多くの Hamiltonian が得られます。
一般に、基本関数 $ \ psi_j $ についてこれ以上の仮定が行われていない場合は、次のよう h_ にして、{pqrs} = h_ {qpsr} を実行するだけで済みます。 \ tag{★} \ label{eq: hpqrs} \ end{/end{の値は、$p、q $ および $r、s $ が交換から交換された場合、その値が同一であることに注意して、 [電子システムの Quantum モデル](xref:microsoft.quantum.chemistry.concepts.quantummodels) の積分からすぐに見ることができます。

スピン orbitals が実際の値であると想定している場合 (ガウス回転ベースの場合)、次のようにし h_ ます。 {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {spqr} = h_ {qrsp} {★} \ label{、"のように想定されている場合は、上記の symmetries を使用して、Hamiltonian のマトリックス要素を格納するために必要なデータを、$8 ドルの係数で減らすことができます。ただし、これにより、一貫性のある方法でデータを簡単にインポートできるようになります。
幸いなことに、Hamiltonian シミュレーションライブラリには、 [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) から、または [nwchem](http://www.nwchem-sw.org/index.php/Main_Page)から直接、整数ファイルをインポートするために使用できるサブルーチンがあります。

分子回転の積分 ($h \_ {pq} $ および $h \_ {pqrs} $ terms) は、型を使用して表されます。 `OrbitalIntegral` この型は、この対称を表現するために役立つ多くの関数を提供します。
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

数値が同じであるすべての回転積分を列挙するだけでなく、によって表される Hamiltonian に含まれるすべての回転インデックスの一覧が次のように `OrbitalIntegral` 生成されることもあります。
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

を追加して Fermionic Hamiltonian を構築するのではなく `FermionTerm` 、各回転整数に対応するすべての用語が自動的に追加される可能性があります。
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
