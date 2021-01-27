---
title: I Q# マジックコマンド
description: Q#Jupyter notebook を使用した I マジックコマンドのクイックリファレンスページ Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: reference
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb6517b782a82c1cb159951af41df9bfde51c0bb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858530"
---
# <a name="ino-locq-magic-commands"></a>I Q# マジックコマンド

### <a name="general"></a>全般

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): 構成オプションを設定または照会できます。
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): 現在使用可能なすべてのマジックコマンドの一覧を返します。
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): 現在開かれている名前空間とそのエイリアスを一覧表示します。
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): NuGet パッケージを読み込む機能を提供します。
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): このカーネルの現在のパフォーマンスメトリックを報告します。
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): プロジェクト参照を表示または追加する機能を提供し Q# ます。 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): ToffoliSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): 現在の Q# セッションで使用できる操作を一覧表示します。
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): 現在のワークスペースに関連するアクションを提供します。

### <a name="azure-quantum-integration"></a>Azure クォンタムの統合

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Azure Quantum ワークスペースにジョブを送信し、完了するまで待機します。
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
