---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _PQandPQQRTermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 4ba13f42064d9311ffb29dbd9363aa3be978e702
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714366"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="095fc-102">_PQandPQQRTermToPauliMajIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="095fc-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="095fc-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="095fc-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="095fc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="095fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="095fc-105">PQ または PQQR 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="095fc-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="095fc-106">入力</span><span class="sxs-lookup"><span data-stu-id="095fc-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="095fc-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="095fc-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="095fc-108">`GeneratorIndex` PQ または PQQR 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="095fc-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="095fc-109">出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="095fc-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="095fc-110">' GeneratorIndex [] ' は、PQ または PQQR 用語を p の用語として表現します。</span><span class="sxs-lookup"><span data-stu-id="095fc-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>