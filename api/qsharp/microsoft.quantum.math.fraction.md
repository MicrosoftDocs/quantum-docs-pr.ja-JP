---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857513"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="b5ce3-102">ユーザー定義型の分数</span><span class="sxs-lookup"><span data-stu-id="b5ce3-102">Fraction user defined type</span></span>

<span data-ttu-id="b5ce3-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b5ce3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b5ce3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5ce3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5ce3-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="b5ce3-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="b5ce3-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="b5ce3-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="b5ce3-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="b5ce3-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="b5ce3-108">分子: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ce3-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ce3-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="b5ce3-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="b5ce3-110">分母: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ce3-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ce3-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="b5ce3-111">Denominator of the fraction/</span></span>