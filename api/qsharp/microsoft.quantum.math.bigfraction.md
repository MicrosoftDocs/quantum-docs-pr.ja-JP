---
uid: Microsoft.Quantum.Math.BigFraction
title: ユーザー定義型の BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846899"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="34757-102">ユーザー定義型の BigFraction</span><span class="sxs-lookup"><span data-stu-id="34757-102">BigFraction user defined type</span></span>

<span data-ttu-id="34757-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="34757-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="34757-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34757-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34757-105">フォームの有理数を表し `p/q` ます。</span><span class="sxs-lookup"><span data-stu-id="34757-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="34757-106">Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。</span><span class="sxs-lookup"><span data-stu-id="34757-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="34757-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="34757-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="34757-108">分子: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="34757-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="34757-109">分数の分子。</span><span class="sxs-lookup"><span data-stu-id="34757-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="34757-110">分母: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="34757-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="34757-111">分数/の分母</span><span class="sxs-lookup"><span data-stu-id="34757-111">Denominator of the fraction/</span></span>