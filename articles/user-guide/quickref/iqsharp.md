---
title: IQ# マジック コマンド
description: 'Q # Jupyter Notebook を使用した IQ # マジックコマンドのクイックリファレンスページ'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431021"
---
# <a name="iq-magic-commands"></a>IQ# マジック コマンド

### <a name="general"></a>全般

- `%config`: 構成設定を設定または取得します。
- `%estimate`: QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- `%lsmagic`: 現在使用可能なすべてのマジックコマンドの一覧を返します。
- `%package`: Nuget パッケージを読み込む機能を提供します。
- `%performance`: このカーネルの現在のパフォーマンスメトリックを報告します。
- `%simulate`: QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。
- `%toffoli`: ToffoliSimulator シミュレーターターゲットコンピューターで指定された関数または操作を実行します。
- `%who`: 現在のワークスペースに関連するアクションを提供します。
- `%workspace`: 現在のセッションで定義されているすべての操作と関数の一覧を、対話的に、または現在のワークスペースから読み込んで返します。

### <a name="chemistry"></a>科学

- `%chemistry.broombridge`: 指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。
- `%chemistry.encode`: Hamiltonian on にあるは、Q # で利用できる形式にエンコードします。
- `%chemistry.fh.add_terms`: Hamiltonian 上の対象に用語を追加します。
- `%chemistry.fh.load`: 電子構造の問題のために、Hamiltonian 上にあるので、このデータを読み込みます。 問題はファイルから読み込まれるか、引数として渡されます。
- `%chemistry.inputstate.load`: Broombridge の電子構造問題を読み込み、選択した入力状態を返します。

### <a name="from-microsoftquantumkatas-package"></a>Katas パッケージから

- `%kata`: 1 つのテストを実行し、テストが成功したかどうかを報告します。
- `%check_kata`: 1 つの kata のテストの参照の実装を確認します。
    具体的には、1つのタスクの参照実装をセルに置き換え、テストが成功したかどうかを報告します。
