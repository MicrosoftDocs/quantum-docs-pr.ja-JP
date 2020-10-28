---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: JWOptimizedHTerms ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: d75737f23db84f2a21daff7a0ebcb8ae51feb642
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713965"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="bc12f-102">JWOptimizedHTerms ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="bc12f-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="bc12f-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="bc12f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="bc12f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc12f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc12f-105">Hamiltonian の用語を表すために、C# から Q # に渡されるデータの形式。</span><span class="sxs-lookup"><span data-stu-id="bc12f-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="bc12f-106">表されるデータの意味は、それを受け取るアルゴリズムによって決まります。</span><span class="sxs-lookup"><span data-stu-id="bc12f-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

