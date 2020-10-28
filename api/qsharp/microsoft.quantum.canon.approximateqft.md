---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716774"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="87a11-102">ApproximateQFT 操作</span><span class="sxs-lookup"><span data-stu-id="87a11-102">ApproximateQFT operation</span></span>

<span data-ttu-id="87a11-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87a11-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87a11-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87a11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87a11-105">クォンタムレジスタにおおよそのクォンタムフーリエ変換 (アク FT) を適用します。</span><span class="sxs-lookup"><span data-stu-id="87a11-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="87a11-106">入力</span><span class="sxs-lookup"><span data-stu-id="87a11-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="87a11-107">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87a11-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87a11-108">QFT 回線で発生する制御された Z 回転を排除するレベルを決定する近似パラメーター。</span><span class="sxs-lookup"><span data-stu-id="87a11-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="87a11-109">近似パラメーター a は、Z 回転の排除レベルを決定します。つまり、∈ {0.. n} と Z 回転 2π/2k (k>a が QFT 回線から削除される) です。</span><span class="sxs-lookup"><span data-stu-id="87a11-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="87a11-110">K >= log ₂ (n) + log ₂ (1/ε) + 3 をバインドできることがわかっています。QFT-アク FT | |Εを<します。</span><span class="sxs-lookup"><span data-stu-id="87a11-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="87a11-111">qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="87a11-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="87a11-112">おおよそのクォンタムフーリエ変換が適用される n qubits のクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="87a11-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87a11-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87a11-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="87a11-114">解説</span><span class="sxs-lookup"><span data-stu-id="87a11-114">Remarks</span></span>

<span data-ttu-id="87a11-115">アク FT には、2π/2k と Hadamard ゲートの形式の Z 回転ゲートが必要です。</span><span class="sxs-lookup"><span data-stu-id="87a11-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="87a11-116">入力と出力は、ビッグエンディアンエンコーディングでエンコードされると想定されます。</span><span class="sxs-lookup"><span data-stu-id="87a11-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="87a11-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="87a11-117">References</span></span>

- [<span data-ttu-id="87a11-118">*M.、Beth* 、Appl.exe、Commun のようになります。コンピューター.19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="87a11-118"> *M. Roetteler, Th. Beth* , Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="87a11-119">*D. Coppersmith* arxiv: quant-ph/0201067v1</span><span class="sxs-lookup"><span data-stu-id="87a11-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)