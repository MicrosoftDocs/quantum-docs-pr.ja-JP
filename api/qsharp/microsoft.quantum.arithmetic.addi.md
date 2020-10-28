---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721687"
---
# <a name="addi-operation"></a><span data-ttu-id="bcf0c-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="bcf0c-102">AddI operation</span></span>

<span data-ttu-id="bcf0c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bcf0c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bcf0c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bcf0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bcf0c-105">では、のレジスタサイズに応じて、キャリーとの加算が自動的に選択さ `ys` れます。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bcf0c-106">入力</span><span class="sxs-lookup"><span data-stu-id="bcf0c-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bcf0c-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bcf0c-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bcf0c-108">$n $ ビット加です。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="bcf0c-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bcf0c-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bcf0c-110">少なくとも $n $ qubits を持つ加数。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="bcf0c-111">は結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bcf0c-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcf0c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

