---
title: Symmetries 分子の積分
description: 'Q # OrbitalIntegral 型を使用して分子 symmetries を列挙する方法について説明します。'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904470"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="afb44-103">Symmetries 分子の積分</span><span class="sxs-lookup"><span data-stu-id="afb44-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="afb44-104">クーロン Hamiltonian の固有の対称性は、[電子システムの Quantum モデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)で指定された Hamiltonian であり、相互にやり取りする原子と nuclei について説明しています。これにより、symmetries 内の用語を圧縮するために利用できる多くの Hamiltonian が得られます。</span><span class="sxs-lookup"><span data-stu-id="afb44-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="afb44-105">一般に、基本関数 $ \ psi_j $ についてこれ以上の仮定が行われていない場合は、次のよう h_ にして、{pqrs} = h_ {qpsr} を実行するだけで済みます。 \ tag{★} \ label{eq: hpqrs} \ end{/end{の値は、$p、q $ および $r、s $ が交換から交換された場合、その値が同一であることに注意して、[電子システムの Quantum モデル](xref:microsoft.quantum.chemistry.concepts.quantummodels)の積分からすぐに見ることができます。</span><span class="sxs-lookup"><span data-stu-id="afb44-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="afb44-106">スピン orbitals が実際の値であると想定した場合 (ガウス回転ベースの場合)、次の h_ ようにします。 {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {spqr} = h_ {qrsp} {★} \ label{eq: hpqrsreal} \ end{式} このような仮定がある場合は、上記の symmetries を使用して、Hamiltonian のマトリックス要素を格納するために必要なデータを $8 $ の係数で減らすことができます。ただし、これにより、一貫性のある方法でデータを簡単にインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="afb44-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="afb44-107">幸いなことに、Hamiltonian シミュレーションライブラリには、 [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)から、または[nwchem](http://www.nwchem-sw.org/index.php/Main_Page)から直接、整数ファイルをインポートするために使用できるサブルーチンがあります。</span><span class="sxs-lookup"><span data-stu-id="afb44-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="afb44-108">分子回転の積分 ($h\_{pq} $ と $h\_{pqrs} $ terms) は、この対称を表現するために役立つ多くの関数を提供する `OrbitalIntegral` 型を使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="afb44-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="afb44-109">数値が同じであるすべての回転積分を列挙するだけでなく、`OrbitalIntegral` によって表される Hamiltonian に含まれるすべての回転インデックスの一覧が次のように生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="afb44-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="afb44-110">分子積分からの Fermionic Hamiltonians の構築</span><span class="sxs-lookup"><span data-stu-id="afb44-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="afb44-111">`FermionTerm`s を追加して Fermionic Hamiltonian を構築するのではなく、各回転整数に対応するすべての用語を自動的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="afb44-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="afb44-112">たとえば、次のコードは、すべての permutational symmetries を自動的に列挙し、正規の順序で用語を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="afb44-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
