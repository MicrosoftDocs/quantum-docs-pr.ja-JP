---
title: Quantum Development Kit Toffoli シミュレーター
description: Microsoft QDK Toffoli シミュレーターについて説明します。これは、何百万もの qubits で使用できる特殊な用途のクォンタムシミュレーターです。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276033"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Quantum Development Kit Toffoli シミュレーター

Quantum Development Kit には、Toffoli シミュレーターが用意されています。これは、X、CNOT、およびマルチ制御の X クォンタム操作に制限されているクォンタムアルゴリズムをシミュレートできる特殊な用途のシミュレーターです (すべての従来のロジックと計算を使用できます)。

Toffoli シミュレーターは、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)よりも操作の方がはるかに制限されていますが、はるかに多くの qubits をシミュレートすることもできます。
Toffoli シミュレーターは何百万もの qubits と共に使用できますが、通常、完全な状態シミュレーターは約30に制限されています。
コンピューターで Q # で記述されたクォンタムアルゴリズムの限られたセットを実行し、デバッグすることができます。たとえば、ブール関数を評価する oracles は、これらのゲートを使用して実装できます。したがって、このシミュレーターを使用して、多数の qubits がテストされます。

このクォンタムシミュレーターはクラスを介して公開されてい `ToffoliSimulator` ます。
シミュレーターを使用するには、このクラスのインスタンスを作成し、残りの `Run` パラメーターと共に実行するクォンタム操作のメソッドに渡すだけです。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>その他の操作

は、 `ToffoliSimulator` `R` 結果として `Exp` 得られる操作が id と等しい場合や、累乗 Paulis をサポートしています (やなど) `X` 。

測定とアサートはサポートされていますが、これは Ponly でのみサポートされてい `Z` ます。
測定値の確率は常に0または1になることに注意してください。Toffoli シミュレーターにはランダム性はありません。

`DumpMachine` と `DumpRegister` がサポートされています。
どちらも、 `Z` 各 qubit の現在のベースの状態を出力します (1 行あたり1つの qubit)。

## <a name="qubitcount"></a>QubitCount

既定では、は `ToffoliSimulator` 65536 qubits の領域を割り当てます。
アルゴリズムにこの値以上が必要な場合は、パラメーターの値をコンストラクターに指定することで、qubit カウントを変更でき `qubitCount` ます。
追加の qubit には、追加のメモリが必要であるため、必要な qubit の数を過剰に見積もることには大きなコストはかかりません。

次に例を示します。

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
