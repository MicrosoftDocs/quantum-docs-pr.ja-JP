---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725211"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="0164e-102">DecompositionState ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0164e-102">DecompositionState user defined type</span></span>

<span data-ttu-id="0164e-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0164e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0164e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0164e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0164e-105">変数インデックスに基づく分解中の状態</span><span class="sxs-lookup"><span data-stu-id="0164e-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="0164e-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="0164e-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="0164e-107">Perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0164e-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="0164e-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="0164e-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="0164e-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="0164e-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="0164e-110">説明</span><span class="sxs-lookup"><span data-stu-id="0164e-110">Description</span></span>

<span data-ttu-id="0164e-111">状態は、現在の順列と、左側の制御ゲートに対して現在生成されている関数を保持し、右側の制御ゲートを制御します。</span><span class="sxs-lookup"><span data-stu-id="0164e-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>