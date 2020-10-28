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
# <a name="combinedstructure-function"></a>連結 Edstructure 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


1つ以上の制御された回転を指定した場合、は、モデルパラメーターのインデックスをシフトして1つのレイヤーを返します。これにより、異なるレイヤーが個別のモデルパラメーターによってパラメーター化されます。

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>入力

### <a name="layers--controlledrotation"></a>レイヤー: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

結合するレイヤー。



## <a name="output--controlledrotation"></a>出力: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

他のすべてのレイヤーの連結を表す、制御された回転の1つのレイヤー。