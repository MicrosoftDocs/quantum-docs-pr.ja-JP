---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714856"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="31f54-102">HTermsToGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="31f54-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="31f54-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="31f54-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="31f54-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31f54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31f54-105">インデックスをデータ形式の Hamiltonian term から `HTerm[]` GeneratorIndex に変換します。</span><span class="sxs-lookup"><span data-stu-id="31f54-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="31f54-106">入力</span><span class="sxs-lookup"><span data-stu-id="31f54-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="31f54-107">データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="31f54-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="31f54-108">形式でデータを入力 `HTerm[]` します。</span><span class="sxs-lookup"><span data-stu-id="31f54-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="31f54-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="31f54-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="31f54-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="31f54-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="31f54-111">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31f54-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31f54-112">Hamiltonian の用語のインデックス</span><span class="sxs-lookup"><span data-stu-id="31f54-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="31f54-113">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="31f54-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="31f54-114">で表される Hamiltonian term と `data[idx]` 、によって追加された追加情報を表す GeneratorIndex `termType` 。</span><span class="sxs-lookup"><span data-stu-id="31f54-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>