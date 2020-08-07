---
title: I Q# マジックコマンド
description: Q#Jupyter notebook を使用した I マジックコマンドのクイックリファレンスページ Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb7b5543ef9222e6bab2b1cbbc7e3ebb54863438
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867983"
---
# <a name="ino-locq-magic-commands"></a>I Q# マジックコマンド

### <a name="general"></a>全般

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): 構成オプションを設定または照会できます。
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): 現在使用可能なすべてのマジックコマンドの一覧を返します。
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): NuGet パッケージを読み込む機能を提供します。
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): このカーネルの現在のパフォーマンスメトリックを報告します。
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): ToffoliSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): 現在の Q# セッションで使用できる操作を一覧表示します。
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): 現在のワークスペースに関連するアクションを提供します。

### <a name="azure-quantum-integration"></a>Azure クォンタムの統合

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Azure Quantum ワークスペースでジョブを実行します。
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): 現在の Azure クォンタムワークスペースのジョブの一覧を表示します。
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): 現在の Azure クォンタムワークスペースにジョブの結果を表示します。
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): 現在の Azure クォンタムワークスペースのジョブの状態を表示します。
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Azure Quantum ワークスペースにジョブを送信します。
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Azure Quantum ワークスペースでのジョブ送信のアクティブな実行ターゲットを設定または表示 Q# します。

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>化学 (Microsoft の Quantum パッケージから)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): 指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): の Hamiltonian on が、で利用できる形式にエンコードさ Q# れます。
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Hamiltonian 上の対象に用語を追加します。
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): 電子構造の問題のために、Hamiltonian 上にあるので、このデータを読み込みます。 問題はファイルから読み込まれるか、引数として渡されます。
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Broombridge の電子構造問題を読み込み、選択した入力状態を返します。

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (Katas パッケージから)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): 1 つのテストを実行し、テストが成功したかどうかを報告します。
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): 1 つの kata のテストの参照の実装を確認します。
    具体的には、1つのタスクの参照実装をセルに置き換え、テストが成功したかどうかを報告します。
