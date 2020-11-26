---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225756"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="14106-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="14106-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="14106-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="14106-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="14106-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="14106-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="14106-105">前の PQRS 間のパリティの差を計算します...用語と次の PQRS...句.</span><span class="sxs-lookup"><span data-stu-id="14106-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="14106-106">この違いは補助 qubit で計算されます。</span><span class="sxs-lookup"><span data-stu-id="14106-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="14106-107">入力</span><span class="sxs-lookup"><span data-stu-id="14106-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="14106-108">Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14106-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14106-109">以前の PQRS に対するインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="14106-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="14106-110">Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14106-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14106-111">次の PQRS へのインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="14106-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="14106-112">aux: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14106-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14106-113">パリティ計算の結果が格納される補助 qubit。</span><span class="sxs-lookup"><span data-stu-id="14106-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="14106-114">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14106-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="14106-115">すべての PQRS によって処理された qubit...条項.</span><span class="sxs-lookup"><span data-stu-id="14106-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14106-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14106-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="14106-117">解説</span><span class="sxs-lookup"><span data-stu-id="14106-117">Remarks</span></span>

<span data-ttu-id="14106-118">これは、P < Q < R < S のインデックスが < していることを前提としています...prevPQ と nextPQ の両方。</span><span class="sxs-lookup"><span data-stu-id="14106-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>