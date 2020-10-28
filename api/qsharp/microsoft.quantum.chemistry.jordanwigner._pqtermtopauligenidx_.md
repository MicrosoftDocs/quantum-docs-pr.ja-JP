---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _Pqtermtop# ligenidx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714343"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="7651f-102">_Pqtermtop# ligenidx_ 関数</span><span class="sxs-lookup"><span data-stu-id="7651f-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="7651f-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7651f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7651f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7651f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7651f-105">PQ 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="7651f-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="7651f-106">入力</span><span class="sxs-lookup"><span data-stu-id="7651f-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="7651f-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7651f-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7651f-108">`GeneratorIndex` PQ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="7651f-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7651f-109">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="7651f-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="7651f-110">' GeneratorIndex [] ' は、PQ term としての用語を表現します。</span><span class="sxs-lookup"><span data-stu-id="7651f-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>