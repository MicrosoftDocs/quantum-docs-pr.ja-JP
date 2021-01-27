---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorSystem
title: IdentityGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorSystem
qsharp.summary: Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 6602087cf7fa173a28fc5894f39ec02a67802427
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858133"
---
# <a name="identitygeneratorsystem-function"></a><span data-ttu-id="48c7d-102">IdentityGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="48c7d-102">IdentityGeneratorSystem function</span></span>

<span data-ttu-id="48c7d-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="48c7d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="48c7d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48c7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48c7d-105">Id 進化操作に対応する、ゼロ Hamiltonian と一貫性のあるジェネレーターシステムを返し `H = 0` ます。</span><span class="sxs-lookup"><span data-stu-id="48c7d-105">Returns a generator system consistent with the zero Hamiltonian `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorSystem () : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="output--generatorsystem"></a><span data-ttu-id="48c7d-106">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="48c7d-106">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="48c7d-107">Hamiltonian $H = $0 での進化を表すジェネレーターシステム。</span><span class="sxs-lookup"><span data-stu-id="48c7d-107">A generator system representing evolution under the Hamiltonian $H = 0$.</span></span>