---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854889"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


一連のパラメーター化および制御された回転、回転角度の割り当て、およびモデルによって認識される2つのクラス間のバイアスで構成される、クォンタム分類器モデルについて説明します。

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>名前付き項目

### <a name="structure--controlledrotation"></a>構造: [Controlle入力](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

入力を分類するために使用される制御された回転のシーケンス。
### <a name="parameters--double"></a>パラメーター: [Double](xref:microsoft.quantum.lang-ref.double)[]

指定された分類構造への回転角度の割り当て。
### <a name="bias--double"></a>バイアス: [Double](xref:microsoft.quantum.lang-ref.double)

この分類子によって認識される2つのクラス間のバイアス。

## <a name="references"></a>References

- [arXiv: 1804.00633](https://arxiv.org/abs/1804.00633)