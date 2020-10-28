---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721099"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="218cc-102">IncrementByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="218cc-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="218cc-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="218cc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="218cc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="218cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="218cc-105">整数定数によって、qubit レジスタのモジュール単位インクリメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="218cc-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="218cc-106">説明</span><span class="sxs-lookup"><span data-stu-id="218cc-106">Description</span></span>

<span data-ttu-id="218cc-107">$ `increment` `modulus` と `target` $y $ によってエンコードされた整数を $N $a $ を意味します。</span><span class="sxs-lookup"><span data-stu-id="218cc-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="218cc-108">その後、次の変換が実行されます。 \begin{align} \ket{y} \ mapare \ket{(y + a) \ 演算子名 {mod} N} \end{align} 整数はリトルエンディアン形式でエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="218cc-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="218cc-109">入力</span><span class="sxs-lookup"><span data-stu-id="218cc-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="218cc-110">increment: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="218cc-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="218cc-111">$Y $ に加算する $ $a 整数値。</span><span class="sxs-lookup"><span data-stu-id="218cc-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="218cc-112">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="218cc-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="218cc-113">Mods $y + a $ の整数 $N $。</span><span class="sxs-lookup"><span data-stu-id="218cc-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="218cc-114">ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="218cc-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="218cc-115">`LittleEndian` `increment` $A $ が追加される形式の整数 $y $。</span><span class="sxs-lookup"><span data-stu-id="218cc-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="218cc-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="218cc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="218cc-117">解説</span><span class="sxs-lookup"><span data-stu-id="218cc-117">Remarks</span></span>

<span data-ttu-id="218cc-118">Target の初期値が $N $ より小さく、$ $a $ が $N $ より小さいことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="218cc-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="218cc-119">は <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 、ベースで同じ操作を実装することに注意して `PhaseLittleEndian` ください。</span><span class="sxs-lookup"><span data-stu-id="218cc-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="218cc-120">参照</span><span class="sxs-lookup"><span data-stu-id="218cc-120">See Also</span></span>

- [<span data-ttu-id="218cc-121">IncrementPhaseByModularInteger です。</span><span class="sxs-lookup"><span data-stu-id="218cc-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)