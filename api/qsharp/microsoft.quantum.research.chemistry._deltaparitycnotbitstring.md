---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226079"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="7e949-102">_DeltaParityCNOTbitstring 関数</span><span class="sxs-lookup"><span data-stu-id="7e949-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="7e949-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7e949-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="7e949-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7e949-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="7e949-105">の従来の処理手順 `ApplyDeltaParity` 。</span><span class="sxs-lookup"><span data-stu-id="7e949-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="7e949-106">これにより、2つの PQRS 間でパリティの違いを評価するためのコントロール qubits の一覧が計算されます。長さが偶数の用語。</span><span class="sxs-lookup"><span data-stu-id="7e949-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="7e949-107">入力</span><span class="sxs-lookup"><span data-stu-id="7e949-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="7e949-108">Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7e949-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="7e949-109">Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7e949-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="7e949-110">出力: ([Int](xref:microsoft.quantum.lang-ref.int)、[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="7e949-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="7e949-111">解説</span><span class="sxs-lookup"><span data-stu-id="7e949-111">Remarks</span></span>

<span data-ttu-id="7e949-112">これは、用語の長さが偶数であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7e949-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="7e949-113">任意の2つの用語間のパリティの違いについて、コントロールの一覧を計算します。</span><span class="sxs-lookup"><span data-stu-id="7e949-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="7e949-114">これは、入力リストが昇順で並べ替えられていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7e949-114">This assumes that the input lists is sorted in ascending order.</span></span>