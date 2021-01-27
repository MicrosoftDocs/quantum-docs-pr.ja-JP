---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854963"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="949eb-102">NQubitsRequired 関数</span><span class="sxs-lookup"><span data-stu-id="949eb-102">NQubitsRequired function</span></span>

<span data-ttu-id="949eb-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="949eb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="949eb-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="949eb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="949eb-105">指定されたシーケンシャル分類子を適用するために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="949eb-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="949eb-106">入力</span><span class="sxs-lookup"><span data-stu-id="949eb-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="949eb-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="949eb-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="949eb-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="949eb-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="949eb-109">シーケンシャル分類器が適用されるレジスタの最小サイズ。</span><span class="sxs-lookup"><span data-stu-id="949eb-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>