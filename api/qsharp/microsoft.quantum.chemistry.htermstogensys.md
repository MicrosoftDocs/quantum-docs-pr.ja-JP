---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204115"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="7f8b5-102">HTermsToGenSys 関数</span><span class="sxs-lookup"><span data-stu-id="7f8b5-102">HTermsToGenSys function</span></span>

<span data-ttu-id="7f8b5-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7f8b5-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="7f8b5-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7f8b5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7f8b5-105">データ形式の Hamiltonian を `HTerm[]` GeneratorSystem に変換します。</span><span class="sxs-lookup"><span data-stu-id="7f8b5-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="7f8b5-106">入力</span><span class="sxs-lookup"><span data-stu-id="7f8b5-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="7f8b5-107">データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="7f8b5-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="7f8b5-108">形式でデータを入力 `HTerm[]` します。</span><span class="sxs-lookup"><span data-stu-id="7f8b5-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="7f8b5-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7f8b5-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7f8b5-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="7f8b5-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="7f8b5-111">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="7f8b5-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="7f8b5-112">入力によって表される Hamiltonian を表す GeneratorSystem `data` 。</span><span class="sxs-lookup"><span data-stu-id="7f8b5-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>