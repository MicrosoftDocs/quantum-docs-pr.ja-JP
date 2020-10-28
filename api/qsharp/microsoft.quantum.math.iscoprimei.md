---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723358"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="678f7-102">IsCoprimeI 関数</span><span class="sxs-lookup"><span data-stu-id="678f7-102">IsCoprimeI function</span></span>

<span data-ttu-id="678f7-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="678f7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="678f7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="678f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="678f7-105">$A $ と $b $ が共存している場合は true、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="678f7-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="678f7-106">入力</span><span class="sxs-lookup"><span data-stu-id="678f7-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="678f7-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="678f7-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="678f7-108">primality がテストされている最初の数</span><span class="sxs-lookup"><span data-stu-id="678f7-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="678f7-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="678f7-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="678f7-110">テストされている共同 primality の2番目の数</span><span class="sxs-lookup"><span data-stu-id="678f7-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="678f7-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="678f7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="678f7-112">$A $ と $b $ が共存している場合 (たとえば、最も一般的な除数が 1) の場合は True、それ以外の場合は false です。</span><span class="sxs-lookup"><span data-stu-id="678f7-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>