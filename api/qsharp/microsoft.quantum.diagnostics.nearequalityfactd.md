---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201514"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="c6ac5-102">NearEqualityFactD 関数</span><span class="sxs-lookup"><span data-stu-id="c6ac5-102">NearEqualityFactD function</span></span>

<span data-ttu-id="c6ac5-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c6ac5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c6ac5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6ac5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6ac5-105">古典的な浮動小数点値が、最小の許容範囲 (1e-10) までの予測値を持つことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="c6ac5-106">入力</span><span class="sxs-lookup"><span data-stu-id="c6ac5-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="c6ac5-107">実際: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6ac5-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c6ac5-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="c6ac5-109">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6ac5-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c6ac5-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6ac5-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6ac5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c6ac5-112">解説</span><span class="sxs-lookup"><span data-stu-id="c6ac5-112">Remarks</span></span>

<span data-ttu-id="c6ac5-113">これは、 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ のハードコーディングされたトレランスを使用した場合と同じです {-10} 。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>