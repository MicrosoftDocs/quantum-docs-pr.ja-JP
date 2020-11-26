---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorSystem
title: IdentityGeneratorSystem 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorSystem
qsharp.summary: Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 64e0e5370b232474548487e0431fbbde9e759e68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230567"
---
# <a name="identitygeneratorsystem-function"></a><span data-ttu-id="3cdd5-102">IdentityGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="3cdd5-102">IdentityGeneratorSystem function</span></span>

<span data-ttu-id="3cdd5-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3cdd5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3cdd5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3cdd5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3cdd5-105">Id 進化操作に対応する、ゼロ Hamiltonian と一貫性のあるジェネレーターシステムを返し `H = 0` ます。</span><span class="sxs-lookup"><span data-stu-id="3cdd5-105">Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorSystem () : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="output--generatorsystem"></a><span data-ttu-id="3cdd5-106">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3cdd5-106">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3cdd5-107">Hamiltonian $H = $0 での進化を表すジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="3cdd5-107">A generator system representing evolution under the Hamiltonian $H = 0$.</span></span>