---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723657"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="89c1f-102">ユーザー定義型の分数</span><span class="sxs-lookup"><span data-stu-id="89c1f-102">Fraction user defined type</span></span>

<span data-ttu-id="89c1f-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="89c1f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="89c1f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89c1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89c1f-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="89c1f-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="89c1f-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="89c1f-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="89c1f-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="89c1f-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="89c1f-108">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89c1f-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89c1f-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="89c1f-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="89c1f-110">分母: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89c1f-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89c1f-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="89c1f-111">Denominator of the fraction/</span></span>