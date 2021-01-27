---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 474146e644bcd042e85b917bc43135a674bedce1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846886"
---
# <a name="inversemodi-function"></a><span data-ttu-id="566c1-102">InverseModI 関数</span><span class="sxs-lookup"><span data-stu-id="566c1-102">InverseModI function</span></span>

<span data-ttu-id="566c1-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="566c1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="566c1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="566c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="566c1-105">は $ $b を返します。この場合、$a \ cdot b = 1 (\texttt{modulus}) $ となります。</span><span class="sxs-lookup"><span data-stu-id="566c1-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="566c1-106">入力</span><span class="sxs-lookup"><span data-stu-id="566c1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="566c1-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="566c1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="566c1-108">反転されている数値</span><span class="sxs-lookup"><span data-stu-id="566c1-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="566c1-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="566c1-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="566c1-110">数値の反転に使用される剰余</span><span class="sxs-lookup"><span data-stu-id="566c1-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="566c1-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="566c1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="566c1-112">$ $B $ (&) $a \ cdot b = 1 (\ 演算子 name{mod} \texttt{modulus}) $</span><span class="sxs-lookup"><span data-stu-id="566c1-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>