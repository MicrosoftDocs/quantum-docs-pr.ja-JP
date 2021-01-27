---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846589"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="e35b7-102">IncrementPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="e35b7-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="e35b7-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e35b7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e35b7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e35b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e35b7-105">整数定数によって、qubit レジスタのモジュール単位インクリメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="e35b7-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e35b7-106">説明</span><span class="sxs-lookup"><span data-stu-id="e35b7-106">Description</span></span>

<span data-ttu-id="e35b7-107">$ `increment` `modulus` と `target` $y $ によってエンコードされた整数を $N $a $ を意味します。</span><span class="sxs-lookup"><span data-stu-id="e35b7-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="e35b7-108">その後、次の変換が実行されます。 \begin{align} \ket{y} \ mapare \ket{(y + a) \ 演算子名 {mod} N} \end{align} 整数は、QFT ではリトルエンディアン形式でエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="e35b7-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="e35b7-109">入力</span><span class="sxs-lookup"><span data-stu-id="e35b7-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="e35b7-110">increment: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e35b7-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e35b7-111">$Y $ に加算する $ $a 整数値。</span><span class="sxs-lookup"><span data-stu-id="e35b7-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e35b7-112">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e35b7-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e35b7-113">Mods $y + a $ の整数 $N $。</span><span class="sxs-lookup"><span data-stu-id="e35b7-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="e35b7-114">ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e35b7-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e35b7-115">$ が追加さ $a れる、フェーズでエンコードされたリトルエンディアン形式の整数 $y $ `increment` 。</span><span class="sxs-lookup"><span data-stu-id="e35b7-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e35b7-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e35b7-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e35b7-117">解説</span><span class="sxs-lookup"><span data-stu-id="e35b7-117">Remarks</span></span>

<span data-ttu-id="e35b7-118">は `target` 、の最上位ビットが0に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e35b7-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="e35b7-119">また、target の値が $N $ 未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e35b7-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="e35b7-120">回路図と説明については、 [arXiv: quant-ph/0205095v3 のページ 5](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)の図5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e35b7-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="e35b7-121">参照</span><span class="sxs-lookup"><span data-stu-id="e35b7-121">See Also</span></span>

- [<span data-ttu-id="e35b7-122">IncrementByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="e35b7-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)