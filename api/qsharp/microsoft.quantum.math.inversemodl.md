---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723629"
---
# <a name="inversemodl-function"></a><span data-ttu-id="a6331-102">InverseModL 関数</span><span class="sxs-lookup"><span data-stu-id="a6331-102">InverseModL function</span></span>

<span data-ttu-id="a6331-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a6331-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a6331-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6331-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6331-105">は $ $b を返します。この場合、$a \ cdot b = 1 (\texttt{modulus}) $ となります。</span><span class="sxs-lookup"><span data-stu-id="a6331-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="a6331-106">入力</span><span class="sxs-lookup"><span data-stu-id="a6331-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a6331-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6331-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6331-108">反転されている数値</span><span class="sxs-lookup"><span data-stu-id="a6331-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="a6331-109">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6331-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6331-110">数値の反転に使用される剰余</span><span class="sxs-lookup"><span data-stu-id="a6331-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a6331-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6331-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6331-112">$ $B $ (&) $a \ cdot b = 1 (\ 演算子 name{mod} \texttt{modulus}) $</span><span class="sxs-lookup"><span data-stu-id="a6331-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>