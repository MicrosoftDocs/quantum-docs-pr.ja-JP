---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230091"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="858b7-102">PrepareUniformSuperposition 操作</span><span class="sxs-lookup"><span data-stu-id="858b7-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="858b7-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="858b7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="858b7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="858b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="858b7-105">0 ~ をエンコードする州に対して一様な法則を作成し `nIndices - 1` ます。</span><span class="sxs-lookup"><span data-stu-id="858b7-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="858b7-106">つまり、このユニタリ $U $ は、入力状態が $ \ket{0\cdots 0} $ の場合に、すべての数値の州 $0 $ に対して $M-$1 に対して uniform 法則を作成します。</span><span class="sxs-lookup"><span data-stu-id="858b7-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="858b7-107">つまり、$ $ \begin{align} U\ket {0} = \ frac {\ {1} sqsum_ rt{\ket{j}. {j = 0} ^ {m.-1}</span><span class="sxs-lookup"><span data-stu-id="858b7-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="858b7-108">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="858b7-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="858b7-109">入力</span><span class="sxs-lookup"><span data-stu-id="858b7-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="858b7-110">n インデックス: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="858b7-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="858b7-111">Uniform 法則内で、必要な状態の数を $ $M します。</span><span class="sxs-lookup"><span data-stu-id="858b7-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="858b7-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="858b7-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="858b7-113">数値の状態を形式で格納する qubit レジスタ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="858b7-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="858b7-114">このレジスタは $M-$1 の数値を格納できる必要があり、$ \ket{0\cdots 0} $ という状態で初期化されると想定されています。</span><span class="sxs-lookup"><span data-stu-id="858b7-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="858b7-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="858b7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="858b7-116">解説</span><span class="sxs-lookup"><span data-stu-id="858b7-116">Remarks</span></span>

<span data-ttu-id="858b7-117">操作は adjointable ですが、その場合は、 `indexRegister` が1つ目の状態に対して一様な法則にある必要があり `nIndices` ます。</span><span class="sxs-lookup"><span data-stu-id="858b7-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>