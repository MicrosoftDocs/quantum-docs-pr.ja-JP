---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714833"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="afbfb-102">HTermToGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="afbfb-102">HTermToGenIdx function</span></span>

<span data-ttu-id="afbfb-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="afbfb-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="afbfb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afbfb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afbfb-105">データ形式の Hamiltonian term を `HTerm` GeneratorIndex に変換します。</span><span class="sxs-lookup"><span data-stu-id="afbfb-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="afbfb-106">入力</span><span class="sxs-lookup"><span data-stu-id="afbfb-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="afbfb-107">用語: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="afbfb-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="afbfb-108">形式でデータを入力 `HTerm` します。</span><span class="sxs-lookup"><span data-stu-id="afbfb-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="afbfb-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="afbfb-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="afbfb-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="afbfb-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="afbfb-111">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="afbfb-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="afbfb-112">で表される Hamiltonian term と `term` 、によって追加された追加情報を表す GeneratorIndex `termType` 。</span><span class="sxs-lookup"><span data-stu-id="afbfb-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>