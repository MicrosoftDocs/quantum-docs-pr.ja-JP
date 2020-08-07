---
title: 完全な状態の量子シミュレーター-Quantum 開発キット
description: Q#Microsoft Quantum Development Kit 完全な状態シミュレーターでプログラムを実行する方法について説明します。
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: b15af66123dadae09815cde1966c69b3ce2e9e64
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868340"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Quantum 開発キット (QDK) 完全な状態シミュレーター

QDK には、ローカルコンピューター上のクォンタムコンピューターをシミュレートする完全な状態シミュレーターが用意されています。 完全な状態シミュレーターを使用して、で記述されたクォンタムアルゴリズムを実行およびデバッグし Q# 、最大30個の qubits を利用できます。 完全な状態シミュレーターは、Microsoft Research の[Liq $ Ui | \rangle $](http://stationq.github.io/Liquid/)プラットフォームで使用されるクォンタムシミュレーターに似ています。

## <a name="invoking-and-running-the-full-state-simulator"></a>完全な状態シミュレーターを起動して実行する

完全な状態シミュレーターはクラスを使用して公開し `QuantumSimulator` ます。 詳細については、「 [ Q# プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。

### <a name="invoking-the-simulator-from-c"></a>C からシミュレーターを呼び出す#

クラスのインスタンスを作成し、そのインスタンスを、 `QuantumSimulator` `Run` 追加のパラメーターと共に、クォンタム操作のメソッドに渡します。
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

クラスはインターフェイスを実装しているため `QuantumSimulator` <xref:System.IDisposable> 、 `Dispose` シミュレーターのインスタンスが不要になった場合は、メソッドを呼び出す必要があります。 これを行う最善の方法は、メソッド[を自動的に呼び出すステートメントで](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement)、シミュレーターの宣言と操作をラップすることです `Dispose` 。

### <a name="invoking-the-simulator-from-python"></a>Python からシミュレーターを呼び出す

インポートされた操作で、Python ライブラリの[シミュレート ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)メソッドを使用し Q# Q# ます。

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>コマンドラインからシミュレーターを呼び出す

コマンドラインからプログラムを実行すると、 Q# 完全な状態シミュレーターが既定のターゲットコンピューターになります。 必要に応じて、 **--シミュレーター** (または **-s**ショートカット) パラメーターを使用して、目的のターゲットコンピューターを指定できます。 次のコマンドはいずれも、完全な状態シミュレーターを使用してプログラムを実行します。 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Juptyer Notebook からシミュレーターを呼び出す

この Q# 操作を実行するには、I マジックコマンド[% シミュレート](xref:microsoft.quantum.iqsharp.magic-ref.simulate)を使用し Q# ます。

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>シミュレーターのシード処理

既定では、完全な状態シミュレーターはランダムな数値ジェネレーターを使用して、クォンタムのランダム性をシミュレートします。 テスト目的では、決定的な結果が得られる場合があります。 C# プログラムでは、パラメーターを使用してコンストラクターに乱数ジェネレーターのシードを指定することで、これを実現でき `QuantumSimulator` `randomNumberGeneratorSeed` ます。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>構成 (スレッドを)

完全な状態シミュレーターでは、 [OpenMP](http://www.openmp.org/)を使用して、必要な線形代数を並列化します。 既定では、OpenMP は使用可能なすべてのハードウェアスレッドを使用します。これは、必要な調整によって実際の作業が dwarfs されるため、多くの場合、qubits の数が少ないプログラムは低速で動作することを意味します。 この問題を解決するには、環境変数 `OMP_NUM_THREADS` を小さい数値に設定します。 経験則として、1つのスレッドを最大4つの qubits に構成してから、qubits ごとに1つのスレッドを追加します。 アルゴリズムによっては、変数の調整が必要になる場合があります。

## <a name="see-also"></a>関連項目

- [量子リソース推定器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)
- [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)