---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719714"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="c2e21-102">ReflectAboutInteger 操作</span><span class="sxs-lookup"><span data-stu-id="c2e21-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="c2e21-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c2e21-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c2e21-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2e21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2e21-105">指定された古典的な整数に関するクォンタムレジスタを反映します。</span><span class="sxs-lookup"><span data-stu-id="c2e21-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="c2e21-106">説明</span><span class="sxs-lookup"><span data-stu-id="c2e21-106">Description</span></span>

<span data-ttu-id="c2e21-107">クォンタムレジスタが最初に state $ \ sum_i \ alpha_i \ket{i} $ に指定されている場合、各 $ \ket{i} $ は整数 $i $ を表す基礎状態であり、指定された整数 $ \ket{j} $、$ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ の基礎状態に関するレジスタの状態を反映します。</span><span class="sxs-lookup"><span data-stu-id="c2e21-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="c2e21-108">入力</span><span class="sxs-lookup"><span data-stu-id="c2e21-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="c2e21-109">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2e21-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2e21-110">反映するベース状態のインデックスを作成する古典整数。</span><span class="sxs-lookup"><span data-stu-id="c2e21-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="c2e21-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c2e21-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="c2e21-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2e21-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c2e21-113">解説</span><span class="sxs-lookup"><span data-stu-id="c2e21-113">Remarks</span></span>

<span data-ttu-id="c2e21-114">この操作はインプレースで実装され、追加の補助 qubits が明示的に割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="c2e21-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>