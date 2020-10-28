---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliMajIdx_
title: _V0123TermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7295b510de2621698d48d40ac28e234d0c8915eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714189"
---
# <a name="_v0123termtopaulimajidx_-function"></a><span data-ttu-id="d6635-102">_V0123TermToPauliMajIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="d6635-102">_V0123TermToPauliMajIdx_ function</span></span>

<span data-ttu-id="d6635-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d6635-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d6635-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6635-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6635-105">Paulis の観点から、PQRS 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="d6635-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex[]
```


## <a name="input"></a><span data-ttu-id="d6635-106">入力</span><span class="sxs-lookup"><span data-stu-id="d6635-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="d6635-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d6635-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d6635-108">`GeneratorIndex` PQRS 用語を表す。</span><span class="sxs-lookup"><span data-stu-id="d6635-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="d6635-109">出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span><span class="sxs-lookup"><span data-stu-id="d6635-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span></span>

<span data-ttu-id="d6635-110">' GeneratorIndex [] ' は、PQRS 用語として表現されています。</span><span class="sxs-lookup"><span data-stu-id="d6635-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>