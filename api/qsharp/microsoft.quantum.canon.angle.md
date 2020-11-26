---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219415"
---
# <a name="angle-function"></a><span data-ttu-id="6b182-102">Angle 関数</span><span class="sxs-lookup"><span data-stu-id="6b182-102">Angle function</span></span>

<span data-ttu-id="6b182-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b182-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b182-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b182-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b182-105">の値が奇数の場合は1を返し、 `index` が偶数の場合は-1 を返し `index` ます。</span><span class="sxs-lookup"><span data-stu-id="6b182-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="6b182-106">説明</span><span class="sxs-lookup"><span data-stu-id="6b182-106">Description</span></span>

<span data-ttu-id="6b182-107">値は、反転の角度を決定する特定の代入について、n 変数および関数の Rademacher-Walsh スペクトルの係数の符号に対応します。</span><span class="sxs-lookup"><span data-stu-id="6b182-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="6b182-108">入力</span><span class="sxs-lookup"><span data-stu-id="6b182-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="6b182-109">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b182-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b182-110">整数としての入力割り当て (0 から 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="6b182-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="6b182-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b182-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

