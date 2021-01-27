---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843846"
---
# <a name="addi-operation"></a><span data-ttu-id="9e2d8-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="9e2d8-102">AddI operation</span></span>

<span data-ttu-id="9e2d8-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9e2d8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9e2d8-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9e2d8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9e2d8-105">では、のレジスタサイズに応じて、キャリーとの加算が自動的に選択さ `ys` れます。</span><span class="sxs-lookup"><span data-stu-id="9e2d8-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9e2d8-106">入力</span><span class="sxs-lookup"><span data-stu-id="9e2d8-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9e2d8-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e2d8-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9e2d8-108">$n $ ビット加です。</span><span class="sxs-lookup"><span data-stu-id="9e2d8-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="9e2d8-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e2d8-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9e2d8-110">少なくとも $n $ qubits を持つ加数。</span><span class="sxs-lookup"><span data-stu-id="9e2d8-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="9e2d8-111">は結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="9e2d8-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e2d8-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e2d8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

