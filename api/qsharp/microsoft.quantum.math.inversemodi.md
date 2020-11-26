---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195377"
---
# <a name="inversemodi-function"></a><span data-ttu-id="3244d-102">InverseModI 関数</span><span class="sxs-lookup"><span data-stu-id="3244d-102">InverseModI function</span></span>

<span data-ttu-id="3244d-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3244d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3244d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3244d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3244d-105">は $ $b を返します。この場合、$a \ cdot b = 1 (\texttt{modulus}) $ となります。</span><span class="sxs-lookup"><span data-stu-id="3244d-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3244d-106">入力</span><span class="sxs-lookup"><span data-stu-id="3244d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3244d-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3244d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3244d-108">反転されている数値</span><span class="sxs-lookup"><span data-stu-id="3244d-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="3244d-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3244d-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3244d-110">数値の反転に使用される剰余</span><span class="sxs-lookup"><span data-stu-id="3244d-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="3244d-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3244d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3244d-112">$ $B $ (&) $a \ cdot b = 1 (\ 演算子 name{mod} \texttt{modulus}) $</span><span class="sxs-lookup"><span data-stu-id="3244d-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>