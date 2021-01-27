---
uid: Microsoft.Quantum.Arithmetic.Carry
title: キャリー操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843353"
---
# <a name="carry-operation"></a><span data-ttu-id="8547c-102">キャリー操作</span><span class="sxs-lookup"><span data-stu-id="8547c-102">Carry operation</span></span>

<span data-ttu-id="8547c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8547c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8547c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8547c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8547c-105">元に戻す伝達ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="8547c-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="8547c-106">Qubit でエンコードされたキャリービット `carryIn` と、およびでエンコードされた2つの summand ビットがある `summand1` `summand2` 場合、はのビットごとの xor を計算し、 `carryIn` `summand1` `summand2` qubit で `summand2` は xor は qubit に対してになり `carryOut` ます。</span><span class="sxs-lookup"><span data-stu-id="8547c-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8547c-107">入力</span><span class="sxs-lookup"><span data-stu-id="8547c-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="8547c-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8547c-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8547c-109">実行中の qubit。</span><span class="sxs-lookup"><span data-stu-id="8547c-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="8547c-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8547c-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8547c-111">最初の summand qubit。</span><span class="sxs-lookup"><span data-stu-id="8547c-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="8547c-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8547c-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8547c-113">2番目の summand qubit は、との合計の下位ビットに置き換えられ `summand1` `summand2` ます。</span><span class="sxs-lookup"><span data-stu-id="8547c-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="8547c-114">carryOut: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8547c-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8547c-115">繰越 qubit は、合計のビットの xor になります。</span><span class="sxs-lookup"><span data-stu-id="8547c-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8547c-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8547c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

