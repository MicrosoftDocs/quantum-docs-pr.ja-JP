---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: 連結 Edstructure 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720518"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="efc6a-102">連結 Edstructure 関数</span><span class="sxs-lookup"><span data-stu-id="efc6a-102">CombinedStructure function</span></span>

<span data-ttu-id="efc6a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="efc6a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="efc6a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="efc6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="efc6a-105">1つ以上の制御された回転を指定した場合、は、モデルパラメーターのインデックスをシフトして1つのレイヤーを返します。これにより、異なるレイヤーが個別のモデルパラメーターによってパラメーター化されます。</span><span class="sxs-lookup"><span data-stu-id="efc6a-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="efc6a-106">入力</span><span class="sxs-lookup"><span data-stu-id="efc6a-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="efc6a-107">レイヤー: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="efc6a-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="efc6a-108">結合するレイヤー。</span><span class="sxs-lookup"><span data-stu-id="efc6a-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="efc6a-109">出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="efc6a-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="efc6a-110">他のすべてのレイヤーの連結を表す、制御された回転の1つのレイヤー。</span><span class="sxs-lookup"><span data-stu-id="efc6a-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>