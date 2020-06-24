---
title: 完全な状態シミュレーター
description: 'Microsoft Quantum Development Kit 完全な状態シミュレーターで Q # プログラムを実行する方法について説明します。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275640"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum 開発キット-完全な状態シミュレーター

Quantum Development Kit には、Microsoft Research の[Liq $ Ui | \rangle $](http://stationq.github.io/Liquid/)に似た完全な状態のクォンタムシミュレーターが用意されています。
このシミュレーターを使用すると、コンピューターの Q # で記述されたクォンタムアルゴリズムを実行およびデバッグできます。

このクォンタムシミュレーターはクラスを介して公開されてい `QuantumSimulator` ます。 シミュレーターを使用するには、このクラスのインスタンスを作成し、残りの `Run` パラメーターと共に実行するクォンタム操作のメソッドに渡すだけです。

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator`クラスはを実装する <xref:System.IDisposable> ため、 `Dispose` シミュレーターのインスタンスが使用されなくなると、メソッドを呼び出す必要があります。 これを行う最善の方法は、上の例のように、ステートメント内にシミュレーターをラップすることです `using` 。

## <a name="seed"></a>Seed

では、 `QuantumSimulator` 乱数ジェネレーターを使用して、クォンタムのランダム性をシミュレートします。 テスト目的では、決定的な結果が得られる場合があります。 これを実現するには、パラメーターを使用して、のコンストラクターに乱数ジェネレーターのシードを指定し `QuantumSimulator` `randomNumberGeneratorSeed` ます。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

は `QuantumSimulator` [OpenMP](http://www.openmp.org/)を使用して、必要な線形代数を並列化します。 既定では、OpenMP で利用可能なすべてのハードウェア スレッドが使用されます。これは、必要な調整を行って実際の作業を小さくするため、多くの場合、少数の量子ビットを含むプログラムの実行速度が低下することを意味します。 これを修正するには、環境変数 `OMP_NUM_THREADS` を小さい数値に設定します。 経験則として、最大 4 つ程度の量子ビットには 1 つのスレッドが適しています。その後、量子ビットごとにスレッドを追加することをお勧めします。ただし、これはアルゴリズムに大きく依存します。

