---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: ApplySequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720547"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="1ccc0-102">ApplySequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="1ccc0-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="1ccc0-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1ccc0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1ccc0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ccc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ccc0-105">連続した分類子の構造とパラメーター化を指定した場合、は、分類子を qubits のレジスタに適用します。</span><span class="sxs-lookup"><span data-stu-id="1ccc0-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1ccc0-106">入力</span><span class="sxs-lookup"><span data-stu-id="1ccc0-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="1ccc0-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="1ccc0-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="1ccc0-108">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1ccc0-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1ccc0-109">分類子の適用先となるターゲットレジスタ。</span><span class="sxs-lookup"><span data-stu-id="1ccc0-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ccc0-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ccc0-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

