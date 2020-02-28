---
title: Quantum Development Kit Toffoli シミュレーター
description: Microsoft QDK Toffoli シミュレーターについて説明します。これは、何百万もの qubits で使用できる特殊な用途のクォンタムシミュレーターです。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907020"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Quantum Development Kit Toffoli シミュレーター

Quantum Development Kit には、Toffoli シミュレーターが用意されています。これは、X、CNOT、およびマルチ制御の X クォンタム操作に制限されているクォンタムアルゴリズムをシミュレートできる特殊な用途のシミュレーターです (すべての従来のロジックと計算を使用できます)。

Toffoli シミュレーターは、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)よりも操作の方がはるかに制限されていますが、はるかに多くの qubits をシミュレートすることもできます。
Toffoli シミュレーターは何百万もの qubits と共に使用できますが、通常、完全な状態シミュレーターは約30に制限されています。
コンピューターで Q # で記述されたクォンタムアルゴリズムの限られたセットを実行し、デバッグすることができます。たとえば、ブール関数を評価する oracles は、これらのゲートを使用して実装できます。したがって、このシミュレーターを使用して、多数の qubits がテストされます。

このクォンタムシミュレーターは `ToffoliSimulator` クラスを介して公開されます。
シミュレーターを使用するには、このクラスのインスタンスを作成し、残りのパラメーターと共に実行するクォンタム操作の `Run` メソッドに渡すだけです。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>その他の操作

`ToffoliSimulator` は、結果として得られる操作が `X` または id に等しい場合に、`R` や `Exp`などのローテーションと累乗 Paulis をサポートします。

測定とアサートはサポートされていますが、`Z` ベースでのみサポートされています。
測定値の確率は常に0または1になることに注意してください。Toffoli シミュレーターにはランダム性はありません。

`DumpMachine` と `DumpRegister` がサポートされています。
どちらの場合も、各 qubit の現在の `Z`の状態が出力されます (1 行あたり1つの qubit)。

## <a name="qubitcount"></a>QubitCount

既定では、`ToffoliSimulator` によって 65536 qubits の領域が割り当てられます。
アルゴリズムにこの値以上が必要な場合は、コンストラクターに `qubitCount` パラメーターの値を指定して、qubit カウントを変更できます。
追加の qubit には、追加のメモリが必要であるため、必要な qubit の数を過剰に見積もることには大きなコストはかかりません。

例 :

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
