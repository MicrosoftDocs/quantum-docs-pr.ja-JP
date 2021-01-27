---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutation
title: TruthTablesFromPermutation 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutation
qsharp.summary: Collect all functions for controlled gates by folding through all variable indexes
ms.openlocfilehash: 1004296841ae50357f074dc9b0cdebb7e4701e9b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855266"
---
# <a name="truthtablesfrompermutation-function"></a><span data-ttu-id="ae724-102">TruthTablesFromPermutation 関数</span><span class="sxs-lookup"><span data-stu-id="ae724-102">TruthTablesFromPermutation function</span></span>

<span data-ttu-id="ae724-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ae724-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ae724-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae724-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae724-105">すべての変数インデックスをフォールドして、制御されたゲートのすべての関数を収集します</span><span class="sxs-lookup"><span data-stu-id="ae724-105">Collect all functions for controlled gates by folding through all variable indexes</span></span>

```qsharp
function TruthTablesFromPermutation (perm : Int[], variableOrder : Int[]) : (BigInt, Int)[]
```


## <a name="input"></a><span data-ttu-id="ae724-106">入力</span><span class="sxs-lookup"><span data-stu-id="ae724-106">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="ae724-107">perm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ae724-107">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="variableorder--int"></a><span data-ttu-id="ae724-108">変数の順序: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ae724-108">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--bigintint"></a><span data-ttu-id="ae724-109">出力: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="ae724-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

