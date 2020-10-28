---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714203"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="62877-102">_V0123TermToPauliGenIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="62877-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="62877-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="62877-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="62877-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62877-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62877-105">Paulis の観点から、PQRS 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="62877-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="62877-106">入力</span><span class="sxs-lookup"><span data-stu-id="62877-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="62877-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="62877-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="62877-108">`GeneratorIndex` PQRS 用語を表す。</span><span class="sxs-lookup"><span data-stu-id="62877-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="62877-109">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="62877-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="62877-110">' GeneratorIndex [] ' は、PQRS 用語として表現されています。</span><span class="sxs-lookup"><span data-stu-id="62877-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>