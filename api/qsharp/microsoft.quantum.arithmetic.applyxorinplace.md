---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843468"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="66508-102">ApplyXorInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="66508-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="66508-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="66508-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="66508-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66508-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66508-105">古典的な整数と、qubits のレジスタによって表される整数の間のビットごとの XOR 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="66508-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="66508-106">説明</span><span class="sxs-lookup"><span data-stu-id="66508-106">Description</span></span>

<span data-ttu-id="66508-107">`X`整数内の1ビットに基づいて、リトルエンディアンレジスタの qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="66508-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="66508-108">`value`A と y は、でエンコードされた符号なし整数であることを示し `target` 、$ `InPlaceXorLE` \ket{y}\rightarrow \ket{y\oplus a} $ というマップによって指定された操作を実行します。 $-oplus $ はビットごとの排他的 or 演算子です。</span><span class="sxs-lookup"><span data-stu-id="66508-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="66508-109">入力</span><span class="sxs-lookup"><span data-stu-id="66508-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="66508-110">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66508-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66508-111">負でないと見なされる整数。</span><span class="sxs-lookup"><span data-stu-id="66508-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="66508-112">ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="66508-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="66508-113">`value`リトルエンディアンエンコーディングで格納するために使用されるクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="66508-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66508-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66508-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

