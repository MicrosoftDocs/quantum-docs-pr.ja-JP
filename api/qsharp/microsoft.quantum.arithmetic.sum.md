---
uid: Microsoft.Quantum.Arithmetic.Sum
title: 合計操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847748"
---
# <a name="sum-operation"></a><span data-ttu-id="66ba2-102">合計操作</span><span class="sxs-lookup"><span data-stu-id="66ba2-102">Sum operation</span></span>

<span data-ttu-id="66ba2-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="66ba2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="66ba2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66ba2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66ba2-105">元に戻すことができない合計ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="66ba2-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="66ba2-106">Qubit でエンコードされたキャリービット `carryIn` と、とでエンコードされた2つの summand ビットを指定すると `summand1` 、とのビット `summand2` ごとの xor を計算し `carryIn` `summand1` `summand2` `summand2` ます。</span><span class="sxs-lookup"><span data-stu-id="66ba2-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="66ba2-107">入力</span><span class="sxs-lookup"><span data-stu-id="66ba2-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="66ba2-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="66ba2-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="66ba2-109">実行中の qubit。</span><span class="sxs-lookup"><span data-stu-id="66ba2-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="66ba2-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="66ba2-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="66ba2-111">最初の summand qubit。</span><span class="sxs-lookup"><span data-stu-id="66ba2-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="66ba2-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="66ba2-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="66ba2-113">2番目の summand qubit は、との合計の下位ビットに置き換えられ `summand1` `summand2` ます。</span><span class="sxs-lookup"><span data-stu-id="66ba2-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66ba2-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66ba2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="66ba2-115">解説</span><span class="sxs-lookup"><span data-stu-id="66ba2-115">Remarks</span></span>

<span data-ttu-id="66ba2-116">操作とは異なり `Carry` 、この操作では、キャリービットは計算されません。</span><span class="sxs-lookup"><span data-stu-id="66ba2-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>