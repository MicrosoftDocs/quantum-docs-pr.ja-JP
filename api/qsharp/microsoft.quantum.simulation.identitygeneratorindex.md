---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724539"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="cd287-102">IdentityGeneratorIndex 関数</span><span class="sxs-lookup"><span data-stu-id="cd287-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="cd287-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cd287-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cd287-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd287-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd287-105">Id の進化操作に対応する、ゼロ Hamiltonian () と一致するジェネレーターインデックスを返し `H = 0` ます。</span><span class="sxs-lookup"><span data-stu-id="cd287-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="cd287-106">入力</span><span class="sxs-lookup"><span data-stu-id="cd287-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="cd287-107">idxTerm: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd287-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd287-108">この入力は無視され、ユーザー定義型との一貫性のために定義されてい <xref:microsoft.quantum.simulation.generatorsystem> ます。</span><span class="sxs-lookup"><span data-stu-id="cd287-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="cd287-109">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cd287-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cd287-110">Hamiltonian $H = $0 での進化を表すジェネレーターインデックス。</span><span class="sxs-lookup"><span data-stu-id="cd287-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>