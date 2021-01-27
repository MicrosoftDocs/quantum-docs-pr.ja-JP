---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851390"
---
# <a name="inversemodl-function"></a><span data-ttu-id="2309e-102">InverseModL 関数</span><span class="sxs-lookup"><span data-stu-id="2309e-102">InverseModL function</span></span>

<span data-ttu-id="2309e-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2309e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2309e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2309e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2309e-105">は $ $b を返します。この場合、$a \ cdot b = 1 (\texttt{modulus}) $ となります。</span><span class="sxs-lookup"><span data-stu-id="2309e-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="2309e-106">入力</span><span class="sxs-lookup"><span data-stu-id="2309e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2309e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2309e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2309e-108">反転されている数値</span><span class="sxs-lookup"><span data-stu-id="2309e-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="2309e-109">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2309e-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2309e-110">数値の反転に使用される剰余</span><span class="sxs-lookup"><span data-stu-id="2309e-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="2309e-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2309e-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2309e-112">$ $B $ (&) $a \ cdot b = 1 (\ 演算子 name{mod} \texttt{modulus}) $</span><span class="sxs-lookup"><span data-stu-id="2309e-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>