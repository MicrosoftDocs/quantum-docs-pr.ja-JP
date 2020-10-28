---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723288"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="30922-102">FeatureRegisterSize 関数</span><span class="sxs-lookup"><span data-stu-id="30922-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="30922-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="30922-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="30922-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30922-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30922-105">特定の特徴ベクターをエンコードするために必要な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="30922-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="30922-106">入力</span><span class="sxs-lookup"><span data-stu-id="30922-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="30922-107">サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="30922-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="30922-108">Qubit レジスタにエンコードされるサンプルの特徴ベクトル。</span><span class="sxs-lookup"><span data-stu-id="30922-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="30922-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="30922-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="30922-110">Qubit レジスタにエンコードするために必要なサイズ `sample` (qubit の数として表現)。</span><span class="sxs-lookup"><span data-stu-id="30922-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>