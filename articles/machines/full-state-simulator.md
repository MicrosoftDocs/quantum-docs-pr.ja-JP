---
title: 完全な状態シミュレーター
description: 'Microsoft Quantum Development Kit 完全な状態シミュレーターで Q # プログラムを実行する方法について説明します。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906119"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum 開発キット-完全な状態シミュレーター

Quantum Development Kit には、Microsoft Research の[Liq $ Ui | \rangle $](http://stationq.github.io/Liquid/)に似た完全な状態のクォンタムシミュレーターが用意されています。
このシミュレーターを使用すると、コンピューターの Q # で記述されたクォンタムアルゴリズムを実行およびデバッグできます。

このクォンタムシミュレーターは `QuantumSimulator` クラスを介して公開されます。 シミュレーターを使用するには、このクラスのインスタンスを作成し、残りのパラメーターと共に実行するクォンタム操作の `Run` メソッドに渡すだけです。

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator` クラスは <xref:System.IDisposable>を実装しているため、シミュレーターのインスタンスが使用されなくなったら、`Dispose` メソッドを呼び出す必要があります。 これを行う最善の方法は、上記の例のように、シミュレーターを `using` ステートメント内にラップすることです。

## <a name="seed"></a>Seed

`QuantumSimulator` は、乱数ジェネレーターを使用して、クォンタムのランダム性をシミュレートします。 テスト目的では、決定的な結果が得られる場合があります。 これを実現するには、`randomNumberGeneratorSeed` パラメーターを使用して `QuantumSimulator`のコンストラクターに乱数ジェネレーターのシードを指定します。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>スレッド

`QuantumSimulator` は、 [OpenMP](http://www.openmp.org/)を使用して、必要な線形代数を並列化します。 既定では、OpenMP で利用可能なすべてのハードウェア スレッドが使用されます。これは、必要な調整を行って実際の作業を小さくするため、多くの場合、少数の量子ビットを含むプログラムの実行速度が低下することを意味します。 これは、`OMP_NUM_THREADS` 環境変数を小さい数値に設定することによって修正できます。 経験則として、最大 4 つ程度の量子ビットには 1 つのスレッドが適しています。その後、量子ビットごとにスレッドを追加することをお勧めします。ただし、これはアルゴリズムに大きく依存します。

