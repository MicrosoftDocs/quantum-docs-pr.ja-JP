---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _Pqandpqqrtermtop/の Genidx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714371"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="23507-102">_Pqandpqqrtermtop/の Genidx_ 関数</span><span class="sxs-lookup"><span data-stu-id="23507-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="23507-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="23507-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="23507-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23507-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23507-105">PQ または PQQR 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="23507-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="23507-106">入力</span><span class="sxs-lookup"><span data-stu-id="23507-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="23507-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="23507-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="23507-108">`GeneratorIndex` PQ または PQQR 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="23507-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="23507-109">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="23507-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="23507-110">' GeneratorIndex [] ' は、PQ または PQQR 用語を p の用語として表現します。</span><span class="sxs-lookup"><span data-stu-id="23507-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>