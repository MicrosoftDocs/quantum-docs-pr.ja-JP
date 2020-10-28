---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713895"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="4af07-102">OptimizedBlockEncodingGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="4af07-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="4af07-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4af07-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4af07-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4af07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4af07-105">によって記述された Hamiltonian を、 `JWOptimizedHTerms` `GeneratorSystem` p li の観点から表現されたに変換 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="4af07-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="4af07-106">入力</span><span class="sxs-lookup"><span data-stu-id="4af07-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="4af07-107">データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="4af07-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="4af07-108">形式の Hamiltonian の説明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="4af07-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="4af07-109">出力: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4af07-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="4af07-110">Hamiltonian の表現 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="4af07-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>