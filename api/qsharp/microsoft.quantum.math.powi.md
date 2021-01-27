---
uid: Microsoft.Quantum.Math.PowI
title: PowI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowI
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: c4e59f7c398a88485ada9d2b313b93aac530ce02
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857477"
---
# <a name="powi-function"></a><span data-ttu-id="88c01-102">PowI 関数</span><span class="sxs-lookup"><span data-stu-id="88c01-102">PowI function</span></span>

<span data-ttu-id="88c01-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="88c01-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="88c01-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88c01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88c01-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="88c01-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowI (a : Int, power : Int) : Int
```


## <a name="input"></a><span data-ttu-id="88c01-106">入力</span><span class="sxs-lookup"><span data-stu-id="88c01-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="88c01-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88c01-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88c01-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="88c01-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="88c01-109">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88c01-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88c01-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="88c01-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--int"></a><span data-ttu-id="88c01-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88c01-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88c01-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="88c01-112">The power $a^b$</span></span>