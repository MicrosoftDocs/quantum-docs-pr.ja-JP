---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840068"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="618d1-102">TrotterStepSize 関数</span><span class="sxs-lookup"><span data-stu-id="618d1-102">TrotterStepSize function</span></span>

<span data-ttu-id="618d1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="618d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="618d1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="618d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="618d1-105">Trotter シミュレーションアルゴリズムの再帰実装で Trotter ステップサイズを計算します。</span><span class="sxs-lookup"><span data-stu-id="618d1-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="618d1-106">入力</span><span class="sxs-lookup"><span data-stu-id="618d1-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="618d1-107">順序: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="618d1-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="618d1-108">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="618d1-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="618d1-109">解説</span><span class="sxs-lookup"><span data-stu-id="618d1-109">Remarks</span></span>

<span data-ttu-id="618d1-110">この操作では、 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)とは異なるインデックス作成規則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="618d1-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="618d1-111">特に、 `DecomposedIntoTimeStepsCA(_, 4)` _2 (0508139) のスカラー $p (-ラムダ) $ に対応します。</span><span class="sxs-lookup"><span data-stu-id="618d1-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>