---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191025"
---
# <a name="addi-operation"></a><span data-ttu-id="606b0-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="606b0-102">AddI operation</span></span>

<span data-ttu-id="606b0-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="606b0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="606b0-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="606b0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="606b0-105">では、のレジスタサイズに応じて、キャリーとの加算が自動的に選択さ `ys` れます。</span><span class="sxs-lookup"><span data-stu-id="606b0-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="606b0-106">入力</span><span class="sxs-lookup"><span data-stu-id="606b0-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="606b0-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="606b0-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="606b0-108">$n $ ビット加です。</span><span class="sxs-lookup"><span data-stu-id="606b0-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="606b0-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="606b0-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="606b0-110">少なくとも $n $ qubits を持つ加数。</span><span class="sxs-lookup"><span data-stu-id="606b0-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="606b0-111">は結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="606b0-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="606b0-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="606b0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

