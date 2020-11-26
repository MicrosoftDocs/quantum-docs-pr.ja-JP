---
uid: Microsoft.Quantum.Math.BigFraction
title: ユーザー定義型の BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211085"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="68807-102">ユーザー定義型の BigFraction</span><span class="sxs-lookup"><span data-stu-id="68807-102">BigFraction user defined type</span></span>

<span data-ttu-id="68807-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="68807-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="68807-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68807-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68807-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="68807-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="68807-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="68807-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="68807-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="68807-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="68807-108">分子: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68807-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="68807-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="68807-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="68807-110">分母: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68807-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="68807-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="68807-111">Denominator of the fraction/</span></span>