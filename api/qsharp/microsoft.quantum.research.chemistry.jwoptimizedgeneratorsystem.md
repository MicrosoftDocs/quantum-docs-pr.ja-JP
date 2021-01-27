---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 13e3386a612b238c29a9e3368eed8628e8ed9b66
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847031"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="d8f6d-102">JWOptimizedGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="d8f6d-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="d8f6d-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="d8f6d-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="d8f6d-105">によって記述された Hamiltonian を `JWOptimizedHTerms` 、 `GeneratorSystem` `GeneratorIndex` このファイルで定義されている規則に従って表現したに変換します。</span><span class="sxs-lookup"><span data-stu-id="d8f6d-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="d8f6d-106">入力</span><span class="sxs-lookup"><span data-stu-id="d8f6d-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="d8f6d-107">データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="d8f6d-108">形式の Hamiltonian の説明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="d8f6d-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="d8f6d-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d8f6d-110">Hamiltonian の表現 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="d8f6d-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>