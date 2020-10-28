---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713988"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="f49d1-102">JordanWignerGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="f49d1-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="f49d1-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f49d1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f49d1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f49d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f49d1-105">によって記述された Hamiltonian を `JWOptimizedHTerms` 、 `GeneratorSystem` `GeneratorIndex` このファイルで定義されている規則に従って表現したに変換します。</span><span class="sxs-lookup"><span data-stu-id="f49d1-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f49d1-106">入力</span><span class="sxs-lookup"><span data-stu-id="f49d1-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="f49d1-107">データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="f49d1-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="f49d1-108">形式の Hamiltonian の説明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="f49d1-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f49d1-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f49d1-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f49d1-110">Hamiltonian の表現 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="f49d1-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>