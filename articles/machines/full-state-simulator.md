---
title: Quantum 開発キット-完全な状態シミュレーター |Microsoft Docs
description: Microsoft の Quantum 開発キットの完全な状態シミュレーターの概要
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184680"
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

## <a name="seed"></a>シード

`QuantumSimulator` は、乱数ジェネレーターを使用して、クォンタムのランダム性をシミュレートします。 テスト目的では、決定的な結果が得られる場合があります。 これを実現するには、`randomNumberGeneratorSeed` パラメーターを使用して `QuantumSimulator`のコンストラクターに乱数ジェネレーターのシードを指定します。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

`QuantumSimulator` は、 [OpenMP](http://www.openmp.org/)を使用して、必要な線形代数を並列化します。 既定では、OpenMP は使用可能なすべてのハードウェアスレッドを使用します。これは、必要な調整によって実際の作業が dwarf されるため、少数の qubits を持つプログラムの実行速度が低下することを意味します。 これは、`OMP_NUM_THREADS` 環境変数を小さい数値に設定することによって修正できます。 経験則として、1つのスレッドは最大4つの qubits に適しています。また、qubits ごとに追加のスレッドが適していますが、これはアルゴリズムに大きく依存しています。

