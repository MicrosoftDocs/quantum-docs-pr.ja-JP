---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722308"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="4f305-102">IsCoprimeL 関数</span><span class="sxs-lookup"><span data-stu-id="4f305-102">IsCoprimeL function</span></span>

<span data-ttu-id="4f305-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4f305-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4f305-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f305-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f305-105">$A $ と $b $ が共存している場合は true、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="4f305-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4f305-106">入力</span><span class="sxs-lookup"><span data-stu-id="4f305-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4f305-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f305-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f305-108">primality がテストされている最初の数</span><span class="sxs-lookup"><span data-stu-id="4f305-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4f305-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4f305-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4f305-110">テストされている共同 primality の2番目の数</span><span class="sxs-lookup"><span data-stu-id="4f305-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="4f305-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f305-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f305-112">$A $ と $b $ が共存している場合 (たとえば、最も一般的な除数が 1) の場合は True、それ以外の場合は false です。</span><span class="sxs-lookup"><span data-stu-id="4f305-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>