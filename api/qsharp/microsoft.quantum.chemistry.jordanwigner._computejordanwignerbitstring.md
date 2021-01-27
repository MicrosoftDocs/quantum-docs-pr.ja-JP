---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839529"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="b4d32-102">_ComputeJordanWignerBitString 関数</span><span class="sxs-lookup"><span data-stu-id="b4d32-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="b4d32-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b4d32-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b4d32-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b4d32-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b4d32-105">2つの作成/annihilation 演算子を使用して、fermionic 演算子内のインデックスに対して、よりも多くの型の配列の Z 成分を計算します。</span><span class="sxs-lookup"><span data-stu-id="b4d32-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b4d32-106">入力</span><span class="sxs-lookup"><span data-stu-id="b4d32-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="b4d32-107">Nの Mi: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4d32-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4d32-108">システムに搭載されているアドオンの数。</span><span class="sxs-lookup"><span data-stu-id="b4d32-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="b4d32-109">Idxが Mion: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b4d32-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b4d32-110">fermionic 演算子のインデックス。</span><span class="sxs-lookup"><span data-stu-id="b4d32-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b4d32-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b4d32-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b4d32-112">`Bool[]` `true` の適用先となる bitstring `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="b4d32-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="b4d32-113">例</span><span class="sxs-lookup"><span data-stu-id="b4d32-113">Example</span></span>

<span data-ttu-id="b4d32-114">let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]);bitString は [false、false、false、true、true、true、false] です。</span><span class="sxs-lookup"><span data-stu-id="b4d32-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>