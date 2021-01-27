---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 4320f111fe7a367bce0f79b04b37639090ddb838
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837115"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="4912d-102">OptimizedBlockEncodingGeneratorSystem 関数</span><span class="sxs-lookup"><span data-stu-id="4912d-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="4912d-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4912d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4912d-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4912d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4912d-105">によって記述された Hamiltonian を、 `JWOptimizedHTerms` `GeneratorSystem` p li の観点から表現されたに変換 `GeneratorIndex` します。</span><span class="sxs-lookup"><span data-stu-id="4912d-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="4912d-106">入力</span><span class="sxs-lookup"><span data-stu-id="4912d-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="4912d-107">データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="4912d-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="4912d-108">形式の Hamiltonian の説明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="4912d-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="4912d-109">出力: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4912d-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="4912d-110">Hamiltonian の表現 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="4912d-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>