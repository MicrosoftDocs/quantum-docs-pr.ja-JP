---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848441"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="e115f-102">FeatureRegisterSize 関数</span><span class="sxs-lookup"><span data-stu-id="e115f-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="e115f-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e115f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e115f-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e115f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e115f-105">特定の特徴ベクターをエンコードするために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="e115f-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="e115f-106">入力</span><span class="sxs-lookup"><span data-stu-id="e115f-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="e115f-107">サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e115f-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e115f-108">Qubit レジスタにエンコードされるサンプルの特徴ベクトル。</span><span class="sxs-lookup"><span data-stu-id="e115f-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="e115f-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e115f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e115f-110">Qubit レジスタにエンコードするために必要なサイズ `sample` (qubit の数として表現)。</span><span class="sxs-lookup"><span data-stu-id="e115f-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>