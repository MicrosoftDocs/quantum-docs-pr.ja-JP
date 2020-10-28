---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722070"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="bbd26-102">BlockEncodingToReflection 関数</span><span class="sxs-lookup"><span data-stu-id="bbd26-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="bbd26-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bbd26-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bbd26-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbd26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbd26-105">を等価のに変換 `BlockEncoding` `BLockEncodingReflection` します。</span><span class="sxs-lookup"><span data-stu-id="bbd26-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="bbd26-106">つまり、 `BlockEncoding` $H $ of 演算子をエンコードする $U $ という文字列を指定した場合は、 `BlockEncodingReflection` 同じ演算子をエンコードする $U ' $ に変換しますが $U ' ^ ダガー = U ' $ も満たされます。</span><span class="sxs-lookup"><span data-stu-id="bbd26-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="bbd26-107">これにより、$U $ の補助レジスタのサイズが 1 qubit だけ増加します。</span><span class="sxs-lookup"><span data-stu-id="bbd26-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="bbd26-108">入力</span><span class="sxs-lookup"><span data-stu-id="bbd26-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="bbd26-109">blockEncoding: [Blockencoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="bbd26-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="bbd26-110">リフレクションに変換される、$U の ' $ ' という1つの `BlockEncoding` を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbd26-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="bbd26-111">出力: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="bbd26-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="bbd26-112">$U ' $ はレジスタに対して共同で動作し、 `a` `s` $H $ をブロックエンコードし $U ' ^ ダガー = U ' $ を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="bbd26-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbd26-113">解説</span><span class="sxs-lookup"><span data-stu-id="bbd26-113">Remarks</span></span>

<span data-ttu-id="bbd26-114">これにより、$U $ の補助レジスタのサイズが 1 qubit だけ増加します。</span><span class="sxs-lookup"><span data-stu-id="bbd26-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="bbd26-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbd26-115">References</span></span>

- <span data-ttu-id="bbd26-116">Hamiltonian シミュレーション Qubitization Guang Hao Low、Isaac L. 語 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="bbd26-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="bbd26-117">参照</span><span class="sxs-lookup"><span data-stu-id="bbd26-117">See Also</span></span>

- [<span data-ttu-id="bbd26-118">Microsoft. クォンタム. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="bbd26-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="bbd26-119">BlockEncodingReflection です。</span><span class="sxs-lookup"><span data-stu-id="bbd26-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)