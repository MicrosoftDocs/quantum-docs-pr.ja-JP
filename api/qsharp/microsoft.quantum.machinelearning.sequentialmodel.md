---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196176"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="1a8ff-102">SequentialModel ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="1a8ff-102">SequentialModel user defined type</span></span>

<span data-ttu-id="1a8ff-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1a8ff-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1a8ff-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1a8ff-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1a8ff-105">一連のパラメーター化および制御された回転、回転角度の割り当て、およびモデルによって認識される2つのクラス間のバイアスで構成される、クォンタム分類器モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1a8ff-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="1a8ff-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="1a8ff-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="1a8ff-107">構造: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1a8ff-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1a8ff-108">入力を分類するために使用される制御された回転のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="1a8ff-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="1a8ff-109">パラメーター: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a8ff-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1a8ff-110">指定された分類構造への回転角度の割り当て。</span><span class="sxs-lookup"><span data-stu-id="1a8ff-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="1a8ff-111">バイアス: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a8ff-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a8ff-112">この分類子によって認識される2つのクラス間のバイアス。</span><span class="sxs-lookup"><span data-stu-id="1a8ff-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="1a8ff-113">リファレンス</span><span class="sxs-lookup"><span data-stu-id="1a8ff-113">References</span></span>

- [<span data-ttu-id="1a8ff-114">arXiv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="1a8ff-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)