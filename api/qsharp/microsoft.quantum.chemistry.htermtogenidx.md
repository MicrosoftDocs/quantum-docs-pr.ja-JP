---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216032"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="4aaae-102">HTermToGenIdx 関数</span><span class="sxs-lookup"><span data-stu-id="4aaae-102">HTermToGenIdx function</span></span>

<span data-ttu-id="4aaae-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4aaae-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="4aaae-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4aaae-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4aaae-105">データ形式の Hamiltonian term を `HTerm` GeneratorIndex に変換します。</span><span class="sxs-lookup"><span data-stu-id="4aaae-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="4aaae-106">入力</span><span class="sxs-lookup"><span data-stu-id="4aaae-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="4aaae-107">用語: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="4aaae-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="4aaae-108">形式でデータを入力 `HTerm` します。</span><span class="sxs-lookup"><span data-stu-id="4aaae-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="4aaae-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4aaae-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4aaae-110">GeneratorIndex に追加される追加情報。</span><span class="sxs-lookup"><span data-stu-id="4aaae-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="4aaae-111">出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4aaae-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4aaae-112">で表される Hamiltonian term と `term` 、によって追加された追加情報を表す GeneratorIndex `termType` 。</span><span class="sxs-lookup"><span data-stu-id="4aaae-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>