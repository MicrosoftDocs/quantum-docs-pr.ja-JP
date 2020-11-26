---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222968"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="6bc69-102">IncrementByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="6bc69-102">IncrementByInteger operation</span></span>

<span data-ttu-id="6bc69-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6bc69-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6bc69-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bc69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bc69-105">フェーズ回転を使用して、古典的な整数によって署名されていないクォンタムレジスタをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="6bc69-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6bc69-106">説明</span><span class="sxs-lookup"><span data-stu-id="6bc69-106">Description</span></span>

<span data-ttu-id="6bc69-107">は、 `target` リトルエンディアンエンコーディングで $ $x $ の符号なし整数をエンコードし、 `increment` $a $ と等しいとします。</span><span class="sxs-lookup"><span data-stu-id="6bc69-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="6bc69-108">次に、この操作では、ユニタリ $ \ket{x} \ map\ket{x + a} $ を実装します。この場合、加算は $ 2 ^ n $ という剰余が実行されます。ここで、$n = \texttt{Length (target!)}$.</span><span class="sxs-lookup"><span data-stu-id="6bc69-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6bc69-109">入力</span><span class="sxs-lookup"><span data-stu-id="6bc69-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="6bc69-110">increment: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bc69-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bc69-111">のインクリメントに使用する整数 `target` 。</span><span class="sxs-lookup"><span data-stu-id="6bc69-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="6bc69-112">ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6bc69-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6bc69-113">リトルエンディアンエンコーディングを使用して、符号なし整数をエンコードするクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="6bc69-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bc69-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bc69-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

