---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714702"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="108f3-102">_ComputeJordanWignerBitString 関数</span><span class="sxs-lookup"><span data-stu-id="108f3-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="108f3-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="108f3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="108f3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="108f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="108f3-105">2つの作成/annihilation 演算子を使用して、fermionic 演算子内のインデックスに対して、よりも多くの型の配列の Z 成分を計算します。</span><span class="sxs-lookup"><span data-stu-id="108f3-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="108f3-106">入力</span><span class="sxs-lookup"><span data-stu-id="108f3-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="108f3-107">Nの Mi: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="108f3-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="108f3-108">システムに搭載されているアドオンの数。</span><span class="sxs-lookup"><span data-stu-id="108f3-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="108f3-109">Idxが Mion: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="108f3-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="108f3-110">fermionic 演算子のインデックス。</span><span class="sxs-lookup"><span data-stu-id="108f3-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="108f3-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="108f3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="108f3-112">`Bool[]` `true` の適用先となる bitstring `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="108f3-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>