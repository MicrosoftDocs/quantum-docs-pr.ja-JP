---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210677"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="28dd7-102">ユーザー定義型の分数</span><span class="sxs-lookup"><span data-stu-id="28dd7-102">Fraction user defined type</span></span>

<span data-ttu-id="28dd7-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="28dd7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="28dd7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28dd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28dd7-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="28dd7-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="28dd7-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="28dd7-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="28dd7-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="28dd7-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="28dd7-108">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28dd7-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28dd7-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="28dd7-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="28dd7-110">分母: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28dd7-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28dd7-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="28dd7-111">Denominator of the fraction/</span></span>