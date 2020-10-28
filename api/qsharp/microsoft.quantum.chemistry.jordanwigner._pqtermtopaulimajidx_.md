---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b75e9b61e05d6451bab378108c75b10334ac1e44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714329"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="6992b-102">_PQTermToPauliMajIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="6992b-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="6992b-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6992b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6992b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6992b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6992b-105">PQ 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="6992b-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="6992b-106">入力</span><span class="sxs-lookup"><span data-stu-id="6992b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="6992b-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6992b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6992b-108">`GeneratorIndex` PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="6992b-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="6992b-109">出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="6992b-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="6992b-110">' GeneratorIndex [] ' は、PQ term としての用語を表現します。</span><span class="sxs-lookup"><span data-stu-id="6992b-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>