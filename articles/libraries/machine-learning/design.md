---
title: QDK を使用して独自の分類器を設計する
description: 量子回線中心の分類器のサーキットモデルを設計するための基本的な概念について説明します。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630245"
---
# <a name="design-your-own-classifier"></a>独自の分類器を設計する

このガイドでは、量子回線中心の分類器のサーキットモデルの設計の背後にある基本的な概念について説明します。

従来のディープラーニングと同様に、特定のアーキテクチャを選択するための一般的な規則はありません。 問題によっては、アーキテクチャによっては、他よりもパフォーマンスが向上します。 ただし、回線を設計する際に役立ついくつかの概念があります。

- 多数のパラメーターは、より柔軟なモデルを意味します。これは、複雑な分類境界の描画に適している場合もありますが、オーバーフィットの影響を受ける可能性があります。

- Qubits 間の Entangling ゲートは、クォンタムの特徴間の相関関係を把握するために不可欠です。

## <a name="how-to-build-a-classifier-with-q"></a>Q で分類子を作成する方法\#

分類器を作成するには、サーキットモデルでパラメーター化制御循環を連結します。 これを行うには、 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) クォンタム Machine Learning ライブラリで定義されている型を使用できます。 この型は、ターゲットの qubit のインデックス、制御 qubit のインデックスの配列、回転の軸、およびモデルを定義するパラメーターの配列内の関連付けられたパラメーターのインデックスを決定する4つの引数を受け取ります。

分類器の例を見てみましょう。 [ハーフ衛星サンプル](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)では、ファイルで定義されている次の分類子を見つけることができ `Training.qs` ます。

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

ここで定義しているのは、要素の配列を返す関数であり `ControlledRotation` 、パラメーターの配列と共に、バイアスによってが定義され [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) ます。 この型は、クォンタム Machine Learning ライブラリでは基本的なものであり、分類子を定義します。 上の関数で定義されている回線は、データセットの各サンプルに2つの特徴が含まれている分類子の一部です。 そのため、必要なのは2つの qubits だけです。 回路のグラフィカルな表現は次のとおりです。

 ![回路モデルの例](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>ライブラリ関数を使用してゲートのレイヤーを作成する

たとえば、MNIST データセットのような28×28ピクセルの画像など、インスタンスごとに784の機能を持つデータセットがあるとします。 この場合、回線の幅が十分に大きくなり、個々のゲートが個別に作成される可能性がありますが、現実的ではないタスクになります。 このため、Quantum Machine Learning ライブラリには、パラメーター化回転のレイヤーを自動的に生成するための一連のツールが用意されています。 たとえば、関数は、 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 指定された軸に沿って制御されないシングル qubit 回転の配列を返します。レジスタ内の qubit ごとに1つの回転があり、それぞれが異なるモデルパラメーターによってパラメーター化されます。 たとえば、は `LocalRotationsLayer(4, X)` 次のゲートのセットを返します。

 ![ローカルローテーションレイヤー](~/media/local_rotations_layer.PNG)

サーキットの設計を効率化するために使用できるすべてのツールを検出するには、 [Quantum Machine Learning ライブラリの API リファレンスを参照](xref:microsoft.quantum.machinelearning)することをお勧めします。

## <a name="next-steps"></a>次のステップ

 サンプルに用意されている例では、さまざまな構造体を試してみてください。 モデルのパフォーマンスに変更があるかどうかを確認できます。 次のチュートリアル「」で [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) は、データセットを読み込んで、分類子の新しいアーキテクチャを試してみる方法を学習します。
