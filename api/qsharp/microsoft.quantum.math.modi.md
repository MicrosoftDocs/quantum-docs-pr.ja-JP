---
uid: Microsoft.Quantum.Math.ModI
title: ModI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 8f4ff37767e5120b99834a63ed19055ba1806907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848059"
---
# <a name="modi-function"></a><span data-ttu-id="2bd1f-102">ModI 関数</span><span class="sxs-lookup"><span data-stu-id="2bd1f-102">ModI function</span></span>

<span data-ttu-id="2bd1f-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2bd1f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2bd1f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bd1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bd1f-105">別の数値に対する数値の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="2bd1f-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2bd1f-106">入力</span><span class="sxs-lookup"><span data-stu-id="2bd1f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2bd1f-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bd1f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bd1f-108">剰余が返される入力 $a $。</span><span class="sxs-lookup"><span data-stu-id="2bd1f-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="2bd1f-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bd1f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bd1f-110">$A $ の剰余を返す対象となる数値。</span><span class="sxs-lookup"><span data-stu-id="2bd1f-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="2bd1f-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bd1f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bd1f-112">剰余 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="2bd1f-112">The modulus $a \bmod b$.</span></span>