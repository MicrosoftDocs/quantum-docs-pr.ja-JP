---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225603"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="bb017-102">_IdentityTimeDependentGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="bb017-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="bb017-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bb017-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bb017-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb017-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb017-105">Hamiltonian と整合性のあるジェネレーターシステムを返し `H(s) = 0` `s` ます。は schedule パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="bb017-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="bb017-106">入力</span><span class="sxs-lookup"><span data-stu-id="bb017-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="bb017-107">schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb017-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb017-108">この入力は無視され、ユーザー定義型との一貫性のために定義されてい <xref:microsoft.quantum.canon.timedependentgeneratorsystem> ます。</span><span class="sxs-lookup"><span data-stu-id="bb017-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="bb017-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bb017-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bb017-110">すべての $s $ の Hamiltonian $H = $0 の下での進化を表すジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="bb017-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>