---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196414"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="c04c8-102">FeatureRegisterSize 関数</span><span class="sxs-lookup"><span data-stu-id="c04c8-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="c04c8-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c04c8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c04c8-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c04c8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c04c8-105">特定の特徴ベクターをエンコードするために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="c04c8-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="c04c8-106">入力</span><span class="sxs-lookup"><span data-stu-id="c04c8-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="c04c8-107">サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c04c8-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c04c8-108">Qubit レジスタにエンコードされるサンプルの特徴ベクトル。</span><span class="sxs-lookup"><span data-stu-id="c04c8-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="c04c8-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c04c8-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c04c8-110">Qubit レジスタにエンコードするために必要なサイズ `sample` (qubit の数として表現)。</span><span class="sxs-lookup"><span data-stu-id="c04c8-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>