---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842051"
---
# <a name="angle-function"></a><span data-ttu-id="3d95f-102">Angle 関数</span><span class="sxs-lookup"><span data-stu-id="3d95f-102">Angle function</span></span>

<span data-ttu-id="3d95f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3d95f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3d95f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d95f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d95f-105">の値が奇数の場合は1を返し、 `index` が偶数の場合は-1 を返し `index` ます。</span><span class="sxs-lookup"><span data-stu-id="3d95f-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="3d95f-106">説明</span><span class="sxs-lookup"><span data-stu-id="3d95f-106">Description</span></span>

<span data-ttu-id="3d95f-107">値は、反転の角度を決定する特定の代入について、n 変数および関数の Rademacher-Walsh スペクトルの係数の符号に対応します。</span><span class="sxs-lookup"><span data-stu-id="3d95f-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="3d95f-108">入力</span><span class="sxs-lookup"><span data-stu-id="3d95f-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="3d95f-109">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3d95f-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3d95f-110">整数としての入力割り当て (0 から 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="3d95f-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="3d95f-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3d95f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

