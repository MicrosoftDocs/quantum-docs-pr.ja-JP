---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 890e60c4b7c5bc474c9f00b59dac6bfddb0e891b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714147"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="a870b-102">_ZTermToPauliMajIdx_ 関数</span><span class="sxs-lookup"><span data-stu-id="a870b-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="a870b-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a870b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a870b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a870b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a870b-105">Paulis の観点から、Z 語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。</span><span class="sxs-lookup"><span data-stu-id="a870b-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="a870b-106">入力</span><span class="sxs-lookup"><span data-stu-id="a870b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a870b-107">用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a870b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a870b-108">`GeneratorIndex` Z 語を表す。</span><span class="sxs-lookup"><span data-stu-id="a870b-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="a870b-109">出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="a870b-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="a870b-110">' GeneratorIndex [] ' は、Z 語を p の用語として表現します。</span><span class="sxs-lookup"><span data-stu-id="a870b-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>