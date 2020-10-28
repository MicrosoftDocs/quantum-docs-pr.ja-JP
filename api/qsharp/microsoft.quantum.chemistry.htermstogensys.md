---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714842"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="188cf-102">HTermsToGenSys 関数</span><span class="sxs-lookup"><span data-stu-id="188cf-102">HTermsToGenSys function</span></span>

<span data-ttu-id="188cf-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="188cf-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="188cf-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="188cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="188cf-105">データ形式の Hamiltonian を `HTerm[]` GeneratorSystem に変換します。</span><span class="sxs-lookup"><span data-stu-id="188cf-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="188cf-106">入力</span><span class="sxs-lookup"><span data-stu-id="188cf-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="188cf-107">データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="188cf-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="188cf-108">形式でデータを入力 `HTerm[]` します。</span><span class="sxs-lookup"><span data-stu-id="188cf-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="188cf-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="188cf-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="188cf-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="188cf-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="188cf-111">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="188cf-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="188cf-112">入力によって表される Hamiltonian を表す GeneratorSystem `data` 。</span><span class="sxs-lookup"><span data-stu-id="188cf-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>