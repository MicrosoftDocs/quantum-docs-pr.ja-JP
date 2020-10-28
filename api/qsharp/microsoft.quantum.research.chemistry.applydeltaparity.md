---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723979"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="26f0f-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="26f0f-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="26f0f-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="26f0f-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="26f0f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26f0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26f0f-105">前の PQRS 間のパリティの差を計算します...用語と次の PQRS...句.</span><span class="sxs-lookup"><span data-stu-id="26f0f-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="26f0f-106">この違いは補助 qubit で計算されます。</span><span class="sxs-lookup"><span data-stu-id="26f0f-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="26f0f-107">入力</span><span class="sxs-lookup"><span data-stu-id="26f0f-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="26f0f-108">Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26f0f-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="26f0f-109">以前の PQRS に対するインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="26f0f-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="26f0f-110">Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26f0f-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="26f0f-111">次の PQRS へのインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="26f0f-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="26f0f-112">aux: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="26f0f-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="26f0f-113">パリティ計算の結果が格納される補助 qubit。</span><span class="sxs-lookup"><span data-stu-id="26f0f-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="26f0f-114">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="26f0f-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="26f0f-115">すべての PQRS によって処理された qubit...条項.</span><span class="sxs-lookup"><span data-stu-id="26f0f-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26f0f-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26f0f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="26f0f-117">解説</span><span class="sxs-lookup"><span data-stu-id="26f0f-117">Remarks</span></span>

<span data-ttu-id="26f0f-118">これは、P < Q < R < S のインデックスが < していることを前提としています...prevPQ と nextPQ の両方。</span><span class="sxs-lookup"><span data-stu-id="26f0f-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>