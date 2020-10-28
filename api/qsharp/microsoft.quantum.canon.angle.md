---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718490"
---
# <a name="angle-function"></a><span data-ttu-id="dd946-102">Angle 関数</span><span class="sxs-lookup"><span data-stu-id="dd946-102">Angle function</span></span>

<span data-ttu-id="dd946-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd946-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd946-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd946-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd946-105">の値が奇数の場合は1を返し、 `index` が偶数の場合は-1 を返し `index` ます。</span><span class="sxs-lookup"><span data-stu-id="dd946-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="dd946-106">説明</span><span class="sxs-lookup"><span data-stu-id="dd946-106">Description</span></span>

<span data-ttu-id="dd946-107">値は、反転の角度を決定する特定の代入について、n 変数および関数の Rademacher-Walsh スペクトルの係数の符号に対応します。</span><span class="sxs-lookup"><span data-stu-id="dd946-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="dd946-108">入力</span><span class="sxs-lookup"><span data-stu-id="dd946-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="dd946-109">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd946-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd946-110">整数としての入力割り当て (0 から 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="dd946-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="dd946-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd946-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

