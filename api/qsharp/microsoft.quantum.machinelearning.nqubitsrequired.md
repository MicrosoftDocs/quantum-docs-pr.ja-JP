---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723573"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="4ec2a-102">NQubitsRequired 関数</span><span class="sxs-lookup"><span data-stu-id="4ec2a-102">NQubitsRequired function</span></span>

<span data-ttu-id="4ec2a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4ec2a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4ec2a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ec2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ec2a-105">指定されたシーケンシャル分類子を適用するために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="4ec2a-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="4ec2a-106">入力</span><span class="sxs-lookup"><span data-stu-id="4ec2a-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="4ec2a-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="4ec2a-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="4ec2a-108">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4ec2a-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4ec2a-109">シーケンシャル分類器が適用されるレジスタの最小サイズ。</span><span class="sxs-lookup"><span data-stu-id="4ec2a-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>