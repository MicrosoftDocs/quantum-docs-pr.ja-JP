---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719791"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="19d06-102">MultiplyByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="19d06-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="19d06-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="19d06-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="19d06-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19d06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19d06-105">Qubit レジスタで整数定数を使ってモジュール乗算を実行します。</span><span class="sxs-lookup"><span data-stu-id="19d06-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="19d06-106">説明</span><span class="sxs-lookup"><span data-stu-id="19d06-106">Description</span></span>

<span data-ttu-id="19d06-107">$ `modulus` と $a $ を $N し `constMultiplier` てください。</span><span class="sxs-lookup"><span data-stu-id="19d06-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="19d06-108">次に、この操作では、計算基準に基づいて、次のマップによって定義される、"$ $ \begin{align} \ket{y} \ket{(a-cdot y)" $1 $N & \end{align}} N} $ $ $0 $y を実装します。</span><span class="sxs-lookup"><span data-stu-id="19d06-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="19d06-109">入力</span><span class="sxs-lookup"><span data-stu-id="19d06-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="19d06-110">[型の型: Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19d06-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19d06-111">乗数を乗算する定数。</span><span class="sxs-lookup"><span data-stu-id="19d06-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="19d06-112">係数は連にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d06-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="19d06-113">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19d06-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19d06-114">乗算演算が実行され `modulus` ます。</span><span class="sxs-lookup"><span data-stu-id="19d06-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="19d06-115">乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="19d06-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="19d06-116">定数を乗算した数値。</span><span class="sxs-lookup"><span data-stu-id="19d06-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="19d06-117">これは、リトルエンディアン形式で整数をエンコードする qubits の配列です。</span><span class="sxs-lookup"><span data-stu-id="19d06-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19d06-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19d06-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="19d06-119">解説</span><span class="sxs-lookup"><span data-stu-id="19d06-119">Remarks</span></span>

- <span data-ttu-id="19d06-120">回路図と説明については、arXiv のページ8の図7を参照してください [: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="19d06-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="19d06-121">この操作は Arxiv の U ₐに対応し [ます: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="19d06-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>