---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851110"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="d5f69-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="d5f69-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="d5f69-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d5f69-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="d5f69-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d5f69-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="d5f69-105">前の PQRS 間のパリティの差を計算します...用語と次の PQRS...句.</span><span class="sxs-lookup"><span data-stu-id="d5f69-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="d5f69-106">この違いは補助 qubit で計算されます。</span><span class="sxs-lookup"><span data-stu-id="d5f69-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d5f69-107">入力</span><span class="sxs-lookup"><span data-stu-id="d5f69-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="d5f69-108">Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d5f69-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d5f69-109">以前の PQRS に対するインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="d5f69-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="d5f69-110">Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d5f69-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d5f69-111">次の PQRS へのインデックスの一覧...条項.</span><span class="sxs-lookup"><span data-stu-id="d5f69-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="d5f69-112">aux: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d5f69-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d5f69-113">パリティ計算の結果が格納される補助 qubit。</span><span class="sxs-lookup"><span data-stu-id="d5f69-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d5f69-114">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5f69-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5f69-115">すべての PQRS によって処理された qubit...条項.</span><span class="sxs-lookup"><span data-stu-id="d5f69-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5f69-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5f69-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5f69-117">解説</span><span class="sxs-lookup"><span data-stu-id="d5f69-117">Remarks</span></span>

<span data-ttu-id="d5f69-118">これは、P < Q < R < S のインデックスが < していることを前提としています...prevPQ と nextPQ の両方。</span><span class="sxs-lookup"><span data-stu-id="d5f69-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>