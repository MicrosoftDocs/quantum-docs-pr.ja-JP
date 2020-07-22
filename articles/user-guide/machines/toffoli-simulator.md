---
title: Quantum Toffoli シミュレーター-Quantum 開発キット
description: Microsoft QDK Toffoli シミュレーターについて説明します。これは、何百万もの qubits で使用できる特殊な用途のクォンタムシミュレーターです。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870619"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Quantum 開発キット (QDK) Toffoli シミュレーター

QDK Toffoli シミュレーターは、限られたスコープの特別な用途のシミュレーターで、 `X` 、、およびの複数制御されたクォンタム操作のみをサポートしてい `CNOT` `X` ます。 すべての従来のロジックと計算を利用できます。

Toffoli シミュレーターは、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)よりも機能が制限されていますが、はるかに多くの qubits をシミュレートできるという利点があります。 Toffoli シミュレーターは何百万もの qubits と共に使用できますが、完全な状態シミュレーターは約 30 qubits に制限されています。 これは、たとえば、ブール関数を評価する oracles を使用した場合に便利です。サポートされているアルゴリズムの限られたセットを使用して実装し、多数の qubits でテストすることができます。

## <a name="invoking-the-toffoli-simulator"></a>Toffoli シミュレーターの呼び出し

クラスを使用して Toffoli シミュレーターを公開し `ToffoliSimulator` ます。 詳細については、「 [Q # プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。

### <a name="invoking-the-toffoli-simulator-from-c"></a>C から Toffoli シミュレーターを呼び出す#

他のターゲット マシンと同様に、最初に `ToffoliSimulator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。

`QuantumSimulator` クラスとは異なり、`ToffoliSimulator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Python から Toffoli シミュレーターを呼び出す

インポートされた Q # 操作で、Python ライブラリの[toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)メソッドを使用します。

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>コマンドラインからの Toffoli シミュレーターの呼び出し

コマンドラインから Q # プログラムを実行する場合は、 **--シミュレーター** (または **-s**ショートカット) パラメーターを使用して、Toffoli シミュレーターターゲットコンピューターを指定します。 次のコマンドは、リソースの推定機能を使用してプログラムを実行します。 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Juptyer Notebook から Toffoli シミュレーターを呼び出す

"IQ # マジック command [% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) " を使用して Q # 操作を実行します。

```
%toffoli myOperation
```

## <a name="supported-operations"></a>サポート対象の操作

Toffoli シミュレーターは次をサポートします。

* 回転と累乗 Paulis (やなど `R` ) `Exp` は、結果の操作が `X` または id 行列と等しい場合に発生します。
* 測定および[アサート](xref:microsoft.quantum.diagnostics.assertmeasurement)操作。ただし、ponly の場合にのみ実行さ `Z` れます。 測定演算の確率は常に**0**または**1**であることに注意してください。Toffoli シミュレーターにはランダム性はありません。
* `DumpMachine``DumpRegister`関数と関数。
どちらの関数も `Z` 、各 qubit の現在の状態を出力し、1行に1つの qubit を出力します。

## <a name="specifying-the-number-of-qubits"></a>Qubits の数の指定

既定では、 `ToffoliSimulator` インスタンスは 65536 qubits の領域を割り当てます。
アルゴリズムにより多くの qubits が必要な場合は、コンストラクターにパラメーターの値を指定して、qubits カウントを指定でき `qubitCount` ます。
追加の qubit は1バイトのメモリしか必要としないので、必要な qubit の数を過剰に見積もることには大きなコストはかかりません。

次に例を示します。

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>関連項目

- [クォンタムリソースの推定](xref:microsoft.quantum.machines.resources-estimator)
- [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [クォンタムの完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator) 