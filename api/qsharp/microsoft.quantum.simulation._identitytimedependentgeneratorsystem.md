---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710689"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="02ced-102">_IdentityTimeDependentGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="02ced-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="02ced-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="02ced-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="02ced-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02ced-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02ced-105">Hamiltonian と整合性のあるジェネレーターシステムを返し `H(s) = 0` `s` ます。は schedule パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="02ced-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="02ced-106">入力</span><span class="sxs-lookup"><span data-stu-id="02ced-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="02ced-107">schedule: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="02ced-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="02ced-108">この入力は無視され、ユーザー定義型との一貫性のために定義されてい <xref:microsoft.quantum.canon.timedependentgeneratorsystem> ます。</span><span class="sxs-lookup"><span data-stu-id="02ced-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="02ced-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="02ced-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="02ced-110">すべての $s $ の Hamiltonian $H = $0 の下での進化を表すジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="02ced-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>