---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713937"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="7c6db-102">OptimizedBEGeneratorSystem ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="7c6db-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="7c6db-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7c6db-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7c6db-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c6db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c6db-105">`OptimizedBETermIndex` `n` 整数が指定された用語のデータを返す関数 `n` 。最初の用語の数 `Int` と、内のすべての項係数の絶対値の合計を返し `Double` ます。</span><span class="sxs-lookup"><span data-stu-id="7c6db-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

