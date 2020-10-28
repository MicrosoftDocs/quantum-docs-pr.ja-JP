---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720211"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="32563-102">PauliCoefficientFromGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="32563-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="32563-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="32563-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="32563-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32563-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32563-105">によって記述された、によって記述されたの係数を抽出 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="32563-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="32563-106">入力</span><span class="sxs-lookup"><span data-stu-id="32563-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="32563-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="32563-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="32563-108">`GeneratorIndex` Pをエンコードする型。</span><span class="sxs-lookup"><span data-stu-id="32563-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="32563-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="32563-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="32563-110">によって記述される用語の係数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="32563-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>