---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714175"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="71dc3-102">_ZTermToPauliGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="71dc3-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="71dc3-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="71dc3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="71dc3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71dc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71dc3-105">Paulis の観点から、Z 語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="71dc3-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="71dc3-106">入力</span><span class="sxs-lookup"><span data-stu-id="71dc3-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="71dc3-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="71dc3-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="71dc3-108">`GeneratorIndex` Z 語を表す。</span><span class="sxs-lookup"><span data-stu-id="71dc3-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="71dc3-109">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="71dc3-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="71dc3-110">' GeneratorIndex [] ' は、Z 語を p の用語として表現します。</span><span class="sxs-lookup"><span data-stu-id="71dc3-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>