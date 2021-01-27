---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: a75d46ef0b38fbcef99b7ab22454e1b5a9475b11
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837771"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="01a0d-102">JordanWignerGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="01a0d-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="01a0d-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="01a0d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="01a0d-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="01a0d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="01a0d-105">によって記述された Hamiltonian を `JWOptimizedHTerms` 、 `GeneratorSystem` `GeneratorIndex` このファイルで定義されている規則に従って表現したに変換します。</span><span class="sxs-lookup"><span data-stu-id="01a0d-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="01a0d-106">入力</span><span class="sxs-lookup"><span data-stu-id="01a0d-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="01a0d-107">データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="01a0d-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="01a0d-108">形式の Hamiltonian の説明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="01a0d-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="01a0d-109">出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="01a0d-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="01a0d-110">Hamiltonian の表現 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="01a0d-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>