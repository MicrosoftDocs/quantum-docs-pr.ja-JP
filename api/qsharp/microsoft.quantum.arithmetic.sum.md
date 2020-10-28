---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 合計操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719503"
---
# <a name="sum-operation"></a><span data-ttu-id="7fee9-102">合計操作</span><span class="sxs-lookup"><span data-stu-id="7fee9-102">Sum operation</span></span>

<span data-ttu-id="7fee9-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7fee9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7fee9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fee9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fee9-105">元に戻すことができない合計ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="7fee9-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="7fee9-106">Qubit でエンコードされたキャリービット `carryIn` と、とでエンコードされた2つの summand ビットを指定すると `summand1` 、とのビット `summand2` ごとの xor を計算し `carryIn` `summand1` `summand2` `summand2` ます。</span><span class="sxs-lookup"><span data-stu-id="7fee9-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7fee9-107">入力</span><span class="sxs-lookup"><span data-stu-id="7fee9-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="7fee9-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7fee9-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7fee9-109">実行中の qubit。</span><span class="sxs-lookup"><span data-stu-id="7fee9-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="7fee9-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7fee9-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7fee9-111">最初の summand qubit。</span><span class="sxs-lookup"><span data-stu-id="7fee9-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="7fee9-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7fee9-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7fee9-113">2番目の summand qubit は、との合計の下位ビットに置き換えられ `summand1` `summand2` ます。</span><span class="sxs-lookup"><span data-stu-id="7fee9-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7fee9-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fee9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7fee9-115">解説</span><span class="sxs-lookup"><span data-stu-id="7fee9-115">Remarks</span></span>

<span data-ttu-id="7fee9-116">操作とは異なり `Carry` 、この操作では、キャリービットは計算されません。</span><span class="sxs-lookup"><span data-stu-id="7fee9-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>