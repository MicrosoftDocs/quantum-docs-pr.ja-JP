---
title: 量子シミュレーターと Q# プログラム
description: Q# プログラムのターゲット マシンとして使用できる量子シミュレーターについて説明します。
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: f40c63eed60379aa46a0cd9cfdd7d8de8c22c079
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771310"
---
# <a name="quantum-simulators"></a>量子シミュレーター

量子シミュレーターは従来型コンピューターで実行され、Q# プログラムの "*ターゲット マシン*" として動作するソフトウェア プログラムであり、量子プログラムをある環境で実行して、さまざまな演算に量子ビットがどのように反応するかを予測するためのテストを行えるようにします。 この記事では、Quantum Development Kit (QDK) に含まれている量子シミュレーターについて説明します。また、コマンド ラインまたは従来の言語で記述されたドライバー コードなどを使用して、量子シミュレーターに Q# プログラムを渡すさまざまな方法についても説明します。  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Quantum Development Kit (QDK) の量子シミュレーター

量子シミュレーターは、アルゴリズムに対して量子プリミティブを実装する役割を担います。 これには、`H`、`CNOT`、`Measure` などのプリミティブ操作だけでなく、量子ビットの管理と追跡も含まれます。 QDK には、同じ量子アルゴリズムの異なるシミュレーション方法を表すさまざまなクラスの量子シミュレーターが含まれています。 


それぞれの種類の量子シミュレーターは、これらのプリミティブに対して異なる実装を提供できます。 たとえば、[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)では、[量子状態ベクトル](xref:microsoft.quantum.glossary#quantum-state)を完全にシミュレートすることで、量子アルゴリズムが実行されます。一方、[量子コンピューターのトレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)では、実際の量子状態はまったく考慮されません。 代わりに、アルゴリズムのゲート、量子ビット、およびその他のリソースの使用状況を追跡します。

### <a name="quantum-machine-classes"></a>量子マシン クラス

今後、他の種類のシミュレーションや、量子ハードウェアでの実行をサポートするために、QDK に追加の量子マシン クラスが定義される予定です。 基になるコンピューターの実装を変更してもアルゴリズムが一定に保たれるようにすることで、シミュレーションのアルゴリズムのテストとデバッグが簡単になり、アルゴリズムが変更されていないという確信を持って実際のハードウェアで実行できます。

QDK には複数の量子マシン クラスが含まれており、すべて `Microsoft.Quantum.Simulation.Simulators` 名前空間に定義されています。

|シミュレーター |クラス|説明|
|-----|------|---|
|[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | 量子アルゴリズムを実行およびデバッグします。これは約 30 量子ビットに制限されています。 |
|[簡易リソース推定器](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | 量子アルゴリズムを実行するために必要なリソースの最上位レベル分析を実行、千単位の量子ビットをサポートします。|
|[トレースベースのリソース推定器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |アルゴリズムの呼び出しグラフ全体におけるリソース消費の高度な分析を実行し、千単位の量子ビットをサポートします。|
|[Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |`X`、`CNOT`、および複数制御された `X` 量子操作に制限される量子アルゴリズムをシミュレートし、100 万の量子ビットをサポートします。 |

## <a name="invoking-the-quantum-simulator"></a>量子シミュレーターの呼び出し

「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」では、Q# コードを量子シミュレーターに渡す次の 3 つの方法が紹介されています。 

* コマンド ラインを使用する
* Python ホスト プログラムを使用する
* C# ホスト プログラムを使用する

量子コンピュータ－は通常の .NET クラスのインスタンスであるため、.NET クラスと同様に、コンストラクターを呼び出すことによって作成します。 その方法は、Q# プログラムの実行方法によって異なります。

## <a name="next-steps"></a>次のステップ

* さまざまな環境で Q# プログラムのターゲット マシンを呼び出す方法の詳細について、「[Q# プロブラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。
