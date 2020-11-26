---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216015"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="c531b-102">HTermsToGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="c531b-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="c531b-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c531b-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="c531b-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c531b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c531b-105">インデックスをデータ形式の Hamiltonian term から `HTerm[]` GeneratorIndex に変換します。</span><span class="sxs-lookup"><span data-stu-id="c531b-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="c531b-106">入力</span><span class="sxs-lookup"><span data-stu-id="c531b-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="c531b-107">データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="c531b-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="c531b-108">形式でデータを入力 `HTerm[]` します。</span><span class="sxs-lookup"><span data-stu-id="c531b-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="c531b-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c531b-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c531b-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="c531b-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="c531b-111">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c531b-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c531b-112">Hamiltonian の用語のインデックス</span><span class="sxs-lookup"><span data-stu-id="c531b-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="c531b-113">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c531b-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c531b-114">で表される Hamiltonian term と `data[idx]` 、によって追加された追加情報を表す GeneratorIndex `termType` 。</span><span class="sxs-lookup"><span data-stu-id="c531b-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>