---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718459"
---
# <a name="applyand-operation"></a><span data-ttu-id="ea76a-102">ApplyAnd 操作</span><span class="sxs-lookup"><span data-stu-id="ea76a-102">ApplyAnd operation</span></span>

<span data-ttu-id="ea76a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea76a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea76a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea76a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea76a-105">測定を使用して adjoint 演算を実行し、両方のコントロール qubit が1の状態である場合にのみ、指定されたターゲット qubit を反転します。</span><span class="sxs-lookup"><span data-stu-id="ea76a-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ea76a-106">説明</span><span class="sxs-lookup"><span data-stu-id="ea76a-106">Description</span></span>

<span data-ttu-id="ea76a-107">`target`両方のコントロールが1で、 `target` が状態が0であると想定している場合にのみ、を反転させます。</span><span class="sxs-lookup"><span data-stu-id="ea76a-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="ea76a-108">この操作には、T カウント4、T 深度2があり、ヘルパー qubit は必要ないため、が0であることがわかっている場合は、CCNOT 操作に適している可能性があり `target` ます。</span><span class="sxs-lookup"><span data-stu-id="ea76a-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="ea76a-109">この操作の adjoint は測定ベースであり、T ゲートは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ea76a-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="ea76a-110">この操作の制御されたアプリケーションでは、ヘルパー qubit、ゲートは不要であり、 `2^c` `Rz` 深さに対して最適化されていません `c` 。は、操作の2つのコントロールを含むコントロールの全体の数です `ApplyAnd` 。</span><span class="sxs-lookup"><span data-stu-id="ea76a-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="ea76a-111">Adjoint の制御されたアプリケーションでは `2^c - 1` `Rz` 、ゲート (非 adjoint 操作のサイズの2倍の角度)、ヘルパー qubit、および深度に対して最適化されていないゲートが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea76a-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="ea76a-112">入力</span><span class="sxs-lookup"><span data-stu-id="ea76a-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="ea76a-113">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea76a-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea76a-114">最初のコントロールの qubit</span><span class="sxs-lookup"><span data-stu-id="ea76a-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="ea76a-115">control2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea76a-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea76a-116">2番目のコントロール qubit</span><span class="sxs-lookup"><span data-stu-id="ea76a-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ea76a-117">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea76a-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea76a-118">ターゲット補助 qubit;状態は0である必要があります</span><span class="sxs-lookup"><span data-stu-id="ea76a-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea76a-119">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea76a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ea76a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea76a-120">References</span></span>

- <span data-ttu-id="ea76a-121">Cody Jones: 「fault トレラントな Toffoli ゲートのための斬新構造」、「Phys 87、022328、2013 [Arxiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA</span><span class="sxs-lookup"><span data-stu-id="ea76a-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="ea76a-122">Gidney: "半分に of クォンタムの追加", Quantum 2, ページ 74, 2018 [Arxiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="ea76a-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="ea76a-123">Mathias Soeken: "Quantum Oracle 回線とクリスマスツリーパターン"、 [2019 年12月19日のブログ記事](https://msoeken.github.io/blog_qac.html) (注: 複数の制御された構築について説明します)</span><span class="sxs-lookup"><span data-stu-id="ea76a-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>