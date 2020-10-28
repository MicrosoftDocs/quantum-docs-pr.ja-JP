---
uid: Microsoft.Quantum.Math.BigFraction
title: ユーザー定義型の BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723209"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="5c8e6-102">ユーザー定義型の BigFraction</span><span class="sxs-lookup"><span data-stu-id="5c8e6-102">BigFraction user defined type</span></span>

<span data-ttu-id="5c8e6-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5c8e6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5c8e6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c8e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c8e6-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="5c8e6-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="5c8e6-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="5c8e6-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="5c8e6-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="5c8e6-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="5c8e6-108">分子: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5c8e6-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5c8e6-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="5c8e6-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="5c8e6-110">分母: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5c8e6-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5c8e6-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="5c8e6-111">Denominator of the fraction/</span></span>