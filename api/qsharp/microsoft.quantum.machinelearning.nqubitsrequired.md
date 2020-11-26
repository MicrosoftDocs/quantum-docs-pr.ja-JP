---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211663"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="81c82-102">NQubitsRequired 関数</span><span class="sxs-lookup"><span data-stu-id="81c82-102">NQubitsRequired function</span></span>

<span data-ttu-id="81c82-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="81c82-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="81c82-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="81c82-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="81c82-105">指定されたシーケンシャル分類子を適用するために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="81c82-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="81c82-106">入力</span><span class="sxs-lookup"><span data-stu-id="81c82-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="81c82-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="81c82-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="81c82-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81c82-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81c82-109">シーケンシャル分類器が適用されるレジスタの最小サイズ。</span><span class="sxs-lookup"><span data-stu-id="81c82-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>