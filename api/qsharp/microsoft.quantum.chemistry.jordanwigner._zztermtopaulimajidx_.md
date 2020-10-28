---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 8c9223d54585f91e1616021bf0643e558d57589c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714128"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="59023-102">_ZZTermToPauliMajIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="59023-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="59023-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="59023-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="59023-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59023-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59023-105">Paulis の観点から、ZZ 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="59023-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="59023-106">入力</span><span class="sxs-lookup"><span data-stu-id="59023-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="59023-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="59023-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="59023-108">`GeneratorIndex` ZZ 用語を表します。</span><span class="sxs-lookup"><span data-stu-id="59023-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="59023-109">出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="59023-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="59023-110">ZZ term を ' GeneratorIndex [] ' として表現します。</span><span class="sxs-lookup"><span data-stu-id="59023-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>