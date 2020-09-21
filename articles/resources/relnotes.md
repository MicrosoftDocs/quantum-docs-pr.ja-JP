---
title: Quantum Development Kit のリリース ノート
description: Microsoft Quantum 開発キット プレビューの最新の更新について説明します。
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5036b4d401bb775a7fee2252ca26e7725bc19004
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834144"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Microsoft Quantum Development Kit のリリース ノート

この記事には、各 Quantum Development Kit のリリースに関する情報が含まれています。

インストール手順については、[インストール ガイド](xref:microsoft.quantum.install)を参照してください。

更新手順については、[更新ガイド](xref:microsoft.quantum.update)を参照してください。

## <a name="version-01220082513"></a>バージョン0.12.20082513

*リリース日: 2020 年8月25日*

このリリースには、次のものが含まれています。

- 新しい[名前空間](xref:microsoft.quantum.random)で、プログラム内からランダムな値をサンプリングするためのより便利な方法が提供されます。 Q# ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311)、 [qsharp-runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328))
- 新しい[ `DumpOperation` 操作](xref:microsoft.quantum.diagnostics.dumpoperation)による改良された[Microsoft の Quantum 名前空間](xref:microsoft.quantum.diagnostics)と、qubit 割り当てと oracle 呼び出しを制限するための新しい操作。 ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302))
- 現在[ `%project` ](xref:microsoft.quantum.iqsharp.magic-ref.project)の Q# [ `qsharp.projects` ](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) Q# ワークスペースフォルダー外のプロジェクトへの参照をサポートする Python での新しいマジックコマンド (I および API)。 この機能の現在の制限については、「 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 」を参照してください。 
- `.csproj`I/Python ホストのファイルの自動読み込みをサポートし Q# ます。これにより、初期化時に外部プロジェクトまたはパッケージ参照を読み込むことができます。 詳細については、 [ Q# Python および Jupyter notebook で](xref:microsoft.quantum.guide.host-programs)のの使用に関するガイドを参照してください。
- より隣人サンプルが追加されました。
- 単純に調整可能結合が追加されました。
- HiddenShift サンプルを更新しました。
- Grover のアルゴリズムを使用して数独を解決するためのサンプルを追加しました (外部貢献)
- 一般的なバグの修正。

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 、 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)については、closed pr の完全な一覧を参照してください。  

## <a name="version-01220072031"></a>バージョン0.12.20072031

*リリース日: 2020 年7月21日*

このリリースには、次のものが含まれています。

- ノートブック内の開い Q# ている名前空間は、今後のすべてのセル計算で使用できるようになりました。 これにより、たとえば、各コードセルで関連する名前空間を開く必要がなく、ノートブックの上部にあるセルに1回だけ名前空間を開くことができます。 新しいマジックコマンドを実行すると、 `%lsopen` 現在開かれている名前空間の一覧が表示されます。

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 、 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)については、closed pr の完全な一覧を参照してください。  

## <a name="version-01220070124"></a>バージョン0.12.20070124

*リリース日: 2020 年7月2日*

このリリースには、次のものが含まれています。

- `qdk-chem`従来の電子構造の問題のシリアル化形式 (例: FCIDUMP) を[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)に変換するための新しいツール
- [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis)変換と分解に基づく合成アルゴリズムを使用して古典 oracles を適用する一貫の名前空間の新しい関数と操作。
- Q#ここで `%simulate` 、、 `%estimate` 、およびその他のマジックコマンドへの引数を許可します。 詳細については、「 [ `%simulate` マジックコマンドリファレンス](xref:microsoft.quantum.iqsharp.magic-ref.simulate)」を参照してください。
- 新しいフェーズ表示オプション I Q# 。詳細については、「 [ `%config` マジックコマンドリファレンス](xref:microsoft.quantum.iqsharp.magic-ref.config)」を参照してください。
- Q# `qsharp` Conda パッケージ ([qsharp](https://anaconda.org/quantum-engineering/qsharp)と[iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) を使用して、 Q# jupyter および python 機能のローカルインストールを conda 環境に簡単にするために、python パッケージが提供されるようになりました。 詳細については、 [ Q# jupyter Notebook](xref:microsoft.quantum.install.jupyter)および[ Q# Python](xref:microsoft.quantum.install.python)インストールガイドを参照してください。
- シミュレーターを使用する場合、qubits はリリース時には | 0 ⟩状態である必要がなくなりましたが、解放の直前に測定された場合は、自動的にリセットできます。
- 異なる QDK バージョンのライブラリパッケージをユーザーが簡単に使用できるように更新されました。 Q# まったく同じバージョンではなく、メジャー & マイナーバージョン番号のみが一致します。
- 廃止された `Microsoft.Quantum.Primitive.*` 名前空間の削除
- 移動された操作:
  - `Microsoft.Quantum.Intrinsic.Assert` は `Microsoft.Quantum.Diagnostics.AssertMeasurement` になりました
  - `Microsoft.Quantum.Intrinsic.AssertProb` は `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability` になりました
- バグの修正 

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 、 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)については、closed pr の完全な一覧を参照してください。  

## <a name="version-0112006403"></a>バージョン 0.11.2006.403

*リリース日:2020 年 6 月 4 日*

このリリースでは、プロジェクトのコンパイルに影響するバグが修正されました Q# 。

## <a name="version-0112006207"></a>バージョン 0.11.2006.207

*リリース日:2020 年 6 月 3 日*

このリリースには、次のものが含まれています。

- Q#エントリポイントが存在する場合、ノートブックと Python ホストプログラムは失敗しなくなります。 Q#
- アクセス修飾子を使用するための[標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)の更新。
- コンパイラで、組み込みのリライト手順間でのリライト手順のプラグインが許可されるようになりました。
- [API の原則](xref:microsoft.quantum.contributing.api-design)で説明されているスケジュールに従って、いくつかの非推奨の関数と操作が削除されています。 Q# バージョン0.11.2004.2825 で警告なしでビルドされたプログラムとライブラリは、変更せずに引き続き動作します。

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 、 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)については、closed pr の完全な一覧を参照してください。  

> [!NOTE]
> このバージョンには、プロジェクトのコンパイルに影響するバグが含まれてい Q# ます。 新しいリリースにアップグレードすることをお勧めします。

## <a name="version-01120042825"></a>バージョン 0.11.2004.2825

*リリース日:2020 年 4 月 30 日*

このリリースには、次のものが含まれています。

- Q#C# または Python ホストファイルが不要になったアプリケーションの新しいサポート。 アプリケーションの概要については Q# 、 [こちら](xref:microsoft.quantum.install.standalone)を参照してください。
- C# または Python ホスト ファイルが不要になるように、クォンタム乱数ジェネレーターのクイックスタートを更新しました。 更新された[クイックスタート](xref:microsoft.quantum.quickstarts.qrng)をご覧ください。
- Docker イメージのパフォーマンスの向上 Q#

> [!NOTE]
> Q# 現在、新しい属性を使用しているアプリケーションを [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) Python または .net ホストプログラムから呼び出すことはできません。
> 詳細については、[Python](xref:microsoft.quantum.install.python) と [.NET 相互運用性](xref:microsoft.quantum.install.cs)のガイドを参照してください。

## <a name="version-01120033107"></a>バージョン 0.11.2003.3107

*リリース日:2020 年 3 月 31 日*

このリリースには、バージョン 0.11.2003.2506 の軽微なバグ修正が含まれています。

## <a name="version-01120032506"></a>バージョン 0.11.2003.2506

*リリース日:2020 年 3 月 26 日*

このリリースには、次のものが含まれています。

- のアクセス修飾子が新しくサポートされ Q# ています。詳細については、「[ファイル構造](xref:microsoft.quantum.guide.filestructure)」を参照してください。
- .NET Core SDK 3.1 に更新されました

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-01020022610"></a>バージョン 0.10.2002.2610

*リリース日:2020 年 2 月 27 日*

このリリースには、次のものが含まれています。

- 新しい Quantum Machine Learning Library。詳細については、[QML ドキュメント ページ](xref:microsoft.quantum.machine-learning.concepts.intro)を参照してください
- Q#バグの修正によって、NuGet パッケージの読み込み時に最大 10 20 倍のパフォーマンスが向上しました。

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-01020012831"></a>バージョン 0.10.2001.2831

*リリース日:2020 年 1 月 29 日*

このリリースには、次のものが含まれています。

- 新規プロジェクトの作成時に Microsoft.Quantum.Development.Kit NuGet パッケージに代わって使用される新しい Microsoft.Quantum.SDK NuGet パッケージ。 Microsoft.Quantum.Development.Kit NuGet パッケージは、既存のプロジェクトで引き続きサポートされます。 
- Q#新しい Microsoft. Quantum. SDK NuGet packge によって有効化されたコンパイラ拡張機能のサポート。詳細については、 [Github のドキュメント](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler)、[コンパイラ拡張機能のサンプル](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions)、および[ Q# 開発ブログ](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)を参照してください。
- .NET Core 3.1 のサポートが追加されました。古い .NET Core SDK バージョンでビルドすると、問題が発生する可能性があるため、バージョン 3.1.100 をインストールすることを強くお勧めします。
- Microsoft.Quantum.QsCompiler.Experimental 下で新しいコンパイラ変換を使用できます
- 出力状態ベクトルを HTML として公開する新しい機能Q#
- Hadamard および SWAP テスト用の EstimateFrequencyA から Microsoft.Quantum.Characterization のサポートを追加しました
- AmplitudeAmplification 名前空間でスタイルガイドが使用されるようになりました Q#

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-01019120501"></a>バージョン 0.10.1912.0501

*リリース日:2019 年 12 月 5 日*

このリリースには、次のものが含まれています。

- 単体テストの新しいテスト属性。ここで Q# 更新さ[here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)れた API ドキュメントを参照してください。[ここでは](xref:microsoft.quantum.guide.testingdebugging)、更新されたテスト & デバッグガイドを参照してください
- プログラム実行エラーの場合にスタックトレースを追加しました Q#
- [OmniSharp C# Visual Studio Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)の更新により、Visual Studio Code 内のブレークポイントがサポートされるようになります

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-01019111607"></a>バージョン 0.10.1911.1607

*リリース日:2019 年 11 月 17 日*

このリリースには、次のものが含まれています。

- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) と Jupyter ノートブックのパフォーマンスの向上

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  


## <a name="version-0101911307"></a>バージョン 0.10.1911.307

*リリース日:2019 年 11 月 1 日*

このリリースには、次のものが含まれています。

- 言語サーバーを自己完結型の実行可能ファイルとして展開するための Visual Studio 拡張機能 & Visual Studio Code を更新し、.NET Core SDK バージョンの依存関係を排除します。  
- .NET Core 3.0 への移行
- 新しい `Fail` メソッドの導入による、Microsoft.Quantum.Simulation.Core.IOperationFactory への破壊的な変更。 SimulatorBase を拡張しないカスタム シミュレーターのみに影響します。 詳細については、[GitHub で pull request を表示](https://github.com/microsoft/qsharp-runtime/pull/59)してください。
- 非推奨の属性に対する新しいサポート

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-0919093002"></a>バージョン 0.9.1909.3002

*リリース日:2019 年 9 月 30 日*

このリリースには、次のものが含まれています。

- Q#Visual Studio 2019 でのコード補完の新しいサポート (バージョン 16.3 & 後) & Visual Studio Code
- 新しい [Quantum Kata](https://github.com/Microsoft/QuantumKatas) (量子加算器用)

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-09-packagereference-0919082902"></a>バージョン 0.9 (*PackageReference 0.9.1908.2902*)

*リリース日:2019 年 8 月 29 日*

このリリースには、次のものが含まれています。

- での [活用形ステートメント](xref:microsoft.quantum.guide.operationsfunctions#conjugations) の新しいサポート Q#
- "置換"、"ドキュメントの追加"、およびシンプルな配列項目の更新など、コンパイラでの新しいコード アクション
- Visual Studio Code 拡張機能へのインストール テンプレートと新しいプロジェクト コマンドの追加
- [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone) などの ApplyIf 連結子の新しいバリアントの追加
- Jupyter Notebook に変換された追加の [Quantum Katas](https://github.com/Microsoft/QuantumKatas)
- Visual Studio 拡張機能で Visual Studio 2019 が必要になりました

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[コンパイラ](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[ランタイム](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)および [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) については、閉じられた PR の完全な一覧を参照してください。  

ここでは、既存のプログラムをアップグレードする手順だけでなく、変更の概要を示します。  これらの変更の詳細については、 [ Q# dev ブログ](https://devblogs.microsoft.com/qsharp)を参照してください。

## <a name="version-08-packagereference-0819071701"></a>バージョン 0.8 (*PackageReference 0.8.1907.1701*)

*リリース日:2019 年 7 月 12 日*

このリリースには、次のものが含まれています。

- 配列をスライスするための新しいインデックス作成場所。詳細については、[言語リファレンスを参照](xref:microsoft.quantum.guide.expressions#array-slices)してください。
- [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry)でホストされている Dockerfile を追加しました。 [ Q# 詳細に](https://github.com/microsoft/iqsharp/blob/main/README.md)ついては、I リポジトリを参照してください。
- [トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に関する破壊的変更、構成設定の更新、名前の変更。[更新された名前については、.NET API ブラウザー](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)を参照してください。

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)と[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)については、閉じられた PR の完全な一覧を参照してください。  

## <a name="version-07-packagereference-0719053109"></a>バージョン 0.7 (*PackageReference 0.7.1905.3109*)

*リリース日:2019 年 5 月 31 日*

このリリースには、次のものが含まれています。
- 言語への追加 Q# 、 
- 化学ライブラリの更新 
- 新しい数値ライブラリ

[ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)と[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)については、閉じられた PR の完全な一覧を参照してください。  

ここでは、既存のプログラムをアップグレードする手順だけでなく、変更の概要を示します。  これらの変更の詳細については、 [ Q# dev ブログ](https://devblogs.microsoft.com/qsharp)を参照してください。

### <a name="no-locq-language-syntax"></a>Q# 言語の構文
このリリースでは、新しい言語の構文が追加されてい Q# ます。
* [ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)の名前付き項目が追加されます。  
* ユーザー定義型コンストラクターを関数として使用できるようになりました。
* ユーザー定義型の [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) および [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) のサポートが追加されます。
* [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) ループの fixup ブロックが省略可能になりました。
* (演算ではなく) 関数で while ループがサポートされるようになりました。

### <a name="library"></a>ライブラリ 

このリリースでは数値ライブラリが追加されます。[新しい数値ライブラリを使用](xref:microsoft.quantum.numerics.usage)し、[新しいサンプル](https://github.com/microsoft/quantum/tree/main/Numerics)を試す方法の詳細を確認してください。  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。  

このリリースでは、化学ライブラリが再編成され、拡張され、更新されます。
* コンポーネントのモジュール性、拡張性、一般的なコードのクリーンアップを向上させます。  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。
* [多重参照波動関数](xref:microsoft.quantum.chemistry.concepts.multireference) (スパース多重参照波動関数とユニタリ結合クラスターの両方) のサポートが追加されます。  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。
* (ご協力ありがとうございました) [1QBit](https://1qbit.com) の投稿者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)):変分 ansatz を使用したエネルギー評価。 [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。
* [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) スキーマを新しい[バージョン 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2) に更新し、ユニタリ結合クラスターの仕様を追加しています。 [問題 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。
* 化学ライブラリ関数に Python 相互運用性が追加されます。 この[サンプル](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration)をお試しください。 [問題 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。

## <a name="version-061905"></a>バージョン 0.6.1905

*リリース日:2019 年 5 月 3 日*

このリリースには、次のものが含まれています。
- 言語を変更します。 Q# 
- Quantum Development Kit ライブラリの再構築 
- 新しいサンプルの追加 
- バグの修正  [ライブラリ](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)と[サンプル](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)に関するいくつかの PR が閉じられました。  

ここでは、既存のプログラムをアップグレードする手順だけでなく、変更の概要を示します。  これらの変更の詳細については、devblogs.microsoft.com/qsharp を参照してください。

### <a name="no-locq-language-syntax"></a>Q# 言語の構文
このリリースでは、新しい言語の構文が追加されてい Q# ます。
* `+` 演算子を使用する[量子演算 (control および adjoint) の特殊化を表現するための短縮形](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)が追加されます。  古い構文は非推奨になります。  古い構文 (`: adjoint` など) を使用するプログラムは引き続き機能しますが、コンパイル時の警告が生成されます。  
* 既存の配列の変更として配列の作成を表現するために使用できる、[copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) の新しい演算子 `w/` が追加されます。
* 一般的な [apply-and-update ステートメント](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) (`+=`、`w/=` など) が追加されます。
* [オープン ディレクティブ](xref:microsoft.quantum.guide.filestructure#open-directives)で名前空間の短い名前を指定する方法が追加されます。

このリリースでは、set ステートメントの左側で配列要素を指定できなくなりました。  これは、構文では配列が可変であることが示され、実際には、演算の結果が常に変更を伴う新しい配列の作成となっていたためです。  代わりに、同じ結果を得るために、copy-and-update の演算子 `w/` を使用する提案を含む、コンパイラ エラーが生成されます。  

### <a name="library-restructuring"></a>ライブラリの再構築
このリリースでは、一貫した方法での拡張を可能にするために、ライブラリが再編成されます。
* Microsoft.Quantum.Primitive 名前空間の名前が、Microsoft.Quantum.Intrinsic に変更されます。  これらの演算は、ターゲット コンピューターによって実装されます。  Microsoft.Quantum.Primitive 名前空間は非推奨となります。  プログラムで非推奨の名前を使用して演算と関数が呼び出されたときに、ランタイム警告で知らせます。

* Microsoft.Quantum.Canon パッケージの名前が、Microsoft.Quantum.Standard に変更されます。  このパッケージには、ほとんどのプログラムに共通の名前空間が含まれてい Q# ます。  これには次のものが含まれます  
    - 一般的な演算のための Microsoft.Quantum.Canon
    - 汎用算術演算のための Microsoft.Quantum.Arithmetic
    - 量子ビット状態の準備に使用される演算のための Microsoft.Quantum.Preparation
    - シミュレーション機能のための Microsoft.Quantum.Simulation

この変更により、Microsoft.Quatum.Canon 名前空間の 1 つの "open" ステートメントを含むプログラムでは、他の 3 つの新しい名前空間に移動された演算を参照した場合、ビルド エラーが発生する可能性があります。  3 つの新しい名前空間に対して追加の open ステートメントを追加することが、この問題を解決する簡単な方法です。  

* 内部の演算が他の名前空間に再構成されたため、いくつかの名前空間は非推奨になりました。 これらの名前空間を使用するプログラムは引き続き機能し、コンパイル時の警告によって、演算が定義されている名前空間が示されます。  

* <xref:microsoft.quantum.arithmetic.littleendian> のユーザー定義型を使用するために、Microsoft.Quantum.Arithmetic 名前空間が正規化されました。 リトル エンディアンに変換するために必要な場合は、関数 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) を使用します。  

* いくつかの呼び出し許可 (関数および操作) の名前は、 [ Q# スタイルガイド](xref:microsoft.quantum.contributing.style)に準拠するように変更されています。  古い callable の名前は非推奨となります。  古い callable を使用するプログラムでは引き続き、コンパイル時の警告を操作します。 

### <a name="new-samples"></a>新しいサンプル

[ Q# F # ドライバーでを使用するサンプル](https://github.com/Microsoft/Quantum/pull/164)を追加しました。  

**ご協力ありがとうございました。** [http://github.com/Microsoft/Quantum](http://github.com/Microsoft/Quantum ) にあるオープン コード ベースに投稿していただいた方は、次のとおりです。 これらの投稿は、コードの豊富なサンプルに大幅に追加され Q# ます。

* Mathias Soeken ([@msoeken](https://github.com/msoeken)):Oracle 関数の合成。 [PR #135](https://github.com/Microsoft/Quantum/pull/135)。

### <a name="migrating-existing-projects-to-061905"></a>既存のプロジェクトを 0.6.1905 に移行する

QDK を更新する場合は、[インストール ガイド](xref:microsoft.quantum.install)を参照してください。
  
クォンタム開発キットのバージョン0.5 の既存のプロジェクトがある場合は、 Q# これらのプロジェクトを最新バージョンに移行する手順を次に示します。

1. プロジェクトは順にアップグレードする必要があります。  複数のプロジェクトを含むソリューションがある場合は、各プロジェクトを参照順に更新します。
2. コマンドプロンプトからを実行し `dotnet clean` て、既存のバイナリファイルと中間ファイルをすべて削除します。
3. テキスト エディターで、.csproj ファイルを編集して、すべての "Microsoft.Quantum" `PackageReference` のバージョンをバージョン 0.6.1904 に変更し、"Microsoft.Quantum.Canon" パッケージの名前を "Microsoft.Quantum.Standard" に変更します。以下に例を示します。

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. コマンドプロンプトで、次のコマンドを実行します。 `dotnet msbuild`  
5. これを実行した後も、上記の変更のために手動でエラーに対処する必要がある場合があります。  多くの場合、これらのエラーは Visual Studio または Visual Studio Code の IntelliSense でも報告されます。
    - Visual Studio 2019 または Visual Studio Code で、プロジェクトまたはそれを含むソリューションのルート フォルダーを開きます。
    - エディターで qs ファイルを開くと、[ Q# 出力] ウィンドウに言語拡張の出力が表示されます。
    - プロジェクトが正常に読み込まれた (出力ウィンドウに示された) 後、各ファイルを開き、手動で残りのすべての問題に対処します。

> [!NOTE]
> * 0\.6 リリースの場合、Quantum Development Kit に含まれている言語サーバーでは、複数のワークスペースがサポートされません。
> * Visual Studio Code でプロジェクトを操作するには、プロジェクト自体とすべての参照先プロジェクトを含むルート フォルダーを開きます。   
> * Visual Studio でソリューションを操作するには、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  
> * 0\.6 以降に移行されたプロジェクトと、古いパッケージ バージョンを使用しているプロジェクトの間の参照は、サポート**されません**。

## <a name="version-051904"></a>バージョン 0.5.1904

*リリース日:2019 年 4 月 15 日*

このリリースにはバグ修正が含まれています。


## <a name="version-051903"></a>バージョン 0.5.1903

*リリース日:2019 年 3 月 27 日*

このリリースには、次のものが含まれています。

- では、Jupyter Notebook のサポートが追加されています。これにより、について理解するのに役立ち Q# ます。  [新しい Jupyter Notebook のサンプルを確認し、独自のノートブックを作成する方法を学習してください](xref:microsoft.quantum.install)。 

- Quantum Canon ライブラリに整数の加算器算術が追加されます。  [新しい整数の加算器を使用する方法が説明されている](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb)、Jupyter Notebook も参照してください。

- コミュニティによって報告された DumpRegister に関する問題 ([#148](https://github.com/Microsoft/Quantum/issues/148)) のバグ修正。

- [using ステートメント](xref:microsoft.quantum.guide.qubits#allocating-qubits)内から返す機能が追加されました。

- [入門ガイド](xref:microsoft.quantum.install)が改訂されました。


## <a name="version-051902"></a>バージョン 0.5.1902

*リリース日:2019 年 2 月 27 日*

このリリースには、次のものが含まれています。

- クロスプラットフォームの Python ホストのサポートが追加されます。  `qsharp`Python 用パッケージを使用する Q# と、python 内から操作や関数を簡単にシミュレートできます。 Python の相互運用性の詳細については、[こちら](xref:microsoft.quantum.install)を参照してください。 

- Visual Studio と Visual Studio Code の拡張機能で、シンボル (関数や演算など) の名前変更がサポートされるようになりました。

- Visual Studio の拡張機能を Visual Studio 2019 にインストールできるようになりました。

## <a name="version-041901"></a>バージョン 0.4.1901

*リリース日:2019 年 1 月 30 日*

このリリースには、次のものが含まれています。

- 任意のサイズの符号付き整数を表す、新しいプリミティブ型である BigInt のサポートが追加されます。  BigInt 型の詳細については、[こちら](xref:microsoft.quantum.guide.types)を参照してください。
- 新しい Toffoli シミュレーターが追加されます。これは、X、CNOT およびマルチ制御の X 量子演算を非常に多くの量子ビットを使用してシミュレートできる特別な用途の高速シミュレーターです。  Toffoli シミュレーターの詳細については、[こちら](xref:microsoft.quantum.machines.toffoli-simulator)を参照してください。
- クォンタムコンピューターで特定の操作のれを実行するために必要なリソースを推定する単純なリソース推定機能を追加し Q# ます。  詳細については、[リソース推定機能](xref:microsoft.quantum.machines.resources-estimator)に関するページを参照してください。


## <a name="version-0318112802"></a>バージョン 0.3.1811.2802

*リリース日:2018 年 11 月 28 日*

VS Code の拡張機能では使用されていませんが、`event-stream` NPM パッケージに関連する[拡張機能の消去](https://code.visualstudio.com/blogs/2018/11/26/event-stream)時に、フラグが設定され、マーケットプレースから削除されました。 このバージョンでは、拡張機能によってすべての赤いフラグがトリガーされる可能性がある、ランタイム依存関係がすべて削除されます。

拡張機能を既にインストールしている場合は、Visual Studio Marketplace の「[Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode)」にアクセスし、[インストール] をクリックして、拡張機能を再度インストールする必要があります。 ご不便をおかけして申し訳ありません。


## <a name="version-0318111511"></a>バージョン 0.3.1811.1511

*リリース日:2018 年 11 月 20 日*

このリリースでは、一部のユーザーが Visual Studio 拡張機能を正常に読み込むことができないバグが修正されます。

## <a name="version-031811203"></a>バージョン 0.3.1811.203

*リリース日:2018 年 11 月 2 日*

このリリースには、次のようないくつかのバグ修正が含まれています。

* `DumpMachine` を呼び出すと、特定の状況下でシミュレーターの状態が変更される可能性があります。
* 2\.1.403 より前のバージョンの .NET Core を使用して、プロジェクトをビルドするときのコンパイルの警告が削除されました。
* ドキュメント、特に、VS Code または Visual Studio でマウスをポイントしたときに表示されるヒントがクリーンアップされました。

## <a name="version-0318102508"></a>バージョン 0.3.1810.2508

*リリース日:2018 年 10 月 29 日*

このリリースには、新しい言語の機能と改善された開発者エクスペリエンスが含まれています。

* このリリースには、の言語サーバー Q# だけでなく、Visual Studio および Visual Studio Code 用のクライアント統合が含まれています。 これにより、波下線が付いたエラーおよび警告形式での入力時のライブ フィードバックと共に、IntelliSense 機能の新しいセットが有効になります。 
* この更新により、一般的には診断メッセージが大幅に改善され、診断のための移動が容易になり、診断の範囲が正確になり、表示されるホバー情報の詳細が追加されます。
* この Q# 言語は、開発者が一般的な操作を実行する方法と、言語機能をシンプルかつ強力 express クォンタムの計算に拡張するための新機能を統合する方法で拡張されています。  このリリースでは、言語にいくつかの重大な変更が加えられ Q# ています。   

このリリースには、新しい量子化学ライブラリも含まれています。

* 化学ライブラリには、次のような新しいハミルトニアン シミュレーション機能が含まれています。
    - シミュレーションの精度を向上させるための任意の偶数次の鈴木トロッター インテグレーター。
    - $T$ ゲートの複雑さを軽減するための、化学固有の最適化を適用した量子ビット化シミュレーション手法。
* (ハミルトニアンの発祥地として有名な[ランドマーク](https://en.wikipedia.org/wiki/Broom_Bridge)に関する) Broombridge スキーマと呼ばれる、新しいオープン ソース スキーマは、分子の表現をインポートしてシミュレートするために導入されています。
* Broombridge スキーマを使用して定義されている複数の化学的表現が提供されています。  これらのモデルは、オープンソースのハイパフォーマンス計算化学ツールである、[NWChem](http://www.nwchem-sw.org/) によって生成されたものです。
* チュートリアルとサンプルでは、化学ライブラリと Broombridge データ モデルを使用して、次のことを行う方法について説明されています。
    - 化学ライブラリを使用してシンプルなハミルトニアンを構築する
    - 位相推定を使用して、水素化リチウムの基底および励起エネルギーを可視化する。
    - 量子化学シミュレーションのリソースを推定する。
    - Broombridge スキーマによって表される分子のエネルギー レベルを推定する。
* ドキュメントでは、NWChem を使用して、でクォンタムシミュレーション用の追加の化学モデルを生成する方法について説明し Q# ます。

Quantum Development Kit の化学ライブラリの詳細については、[こちら](xref:microsoft.quantum.chemistry.concepts.intro)を参照してください。

新しい化学ライブラリでは、ライブラリを新しい GitHub リポジトリ ([Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries)) に分割します。  サンプルは、リポジトリ [Microsoft/Quantum](https://github.com/Microsoft/Quantum) に残ります。  両方への投稿を歓迎します。

このリリースには、コミュニティによって報告された問題に関するバグの修正と機能が含まれています。

* Intellisense の Q# 場合 ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。
* .qs ファイル ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。
* If ステートメントで中かっこが省略された場合のエラー メッセージを改善する ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。
* 可変 (再) バインドでのタプル分解をサポートする ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。
* 指定された BitFlipCode の実行中のエラー ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。
* H2SimulationGUI に大きなピークが表示されることがある ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。

### <a name="community-contributions"></a>コミュニティへの投稿

**ご協力ありがとうございました。** [http://github.com/Microsoft/Quantum](http://github.com/Microsoft/Quantum ) にあるオープン コード ベースに投稿していただいた方は、次のとおりです。 これらの投稿は、コードの豊富なサンプルに大幅に追加され Q# ます。

* Rolf ( [@RolfHuisman](https://github.com/RolfHuisman) ): Q# qasm をトランスレーターに作成することにより、qasm/開発者のエクスペリエンスを改善しました。 Q# [PR #58](https://github.com/Microsoft/Quantum/pull/58)。

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):非局所性に関連する量子ゲームである、CHSH ゲームを実装するサンプルを投稿しました。  [PR #84](https://github.com/Microsoft/Quantum/pull/84)。

Rohit Gupta ([@guptarohit](https://github.com/guptarohit)、[PR #90](https://github.com/Microsoft/quantum/pull/90))、Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi)、[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289))、Lee James O'Riordan ([@mlxd](https://github.com/mlxd)、[PR #96](https://github.com/Microsoft/Quantum/pull/96)) にも感謝します。皆様のご協力を受け、ドキュメント、スペルおよび入力ミスを修正し、私たち全員のコンテンツを向上させることができました。 

## <a name="version-021809701"></a>バージョン 0.2.1809.701

*リリース日:2018 年 9 月 10 日*

このリリースには、コミュニティによって報告された問題に関するバグの修正が含まれています。 含まれている内容は次のとおりです。

* シフト演算子を使用できない ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。
* コンソールへの出力時に `QCTraceSimulator` で `DumpMachine` / `DumpRegister` が失敗する ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。
* 0 量子ビットの割り当てを許可する ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。
* `AssertQubitState` に明示的な Complex() 呼び出しが必要である ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。
* macOS での `Measure` 演算で常に `One` が返される ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。

よろしくお願いいたします。 

## <a name="version-0218063001"></a>バージョン 0.2.1806.3001

*リリース日:2018 年 6 月 30 日*

このリリースは、 [GitHub で報告](https://github.com/Microsoft/Quantum/issues/48) された問題 #48 の簡単な修正にすぎ Q# ません (ユーザー名に空白が含まれている場合、コンパイルは失敗します)。 対応する新しいバージョン (`0.2.1806.3001-preview`) で、`0.2.1806.1503` と同じ更新手順に従ってください。

## <a name="version-0218061503"></a>バージョン 0.2.1806.1503

*リリース日:2018 年 6 月 22 日*

このリリースには、改善されたデバッグ エクスペリエンスとパフォーマンスだけでなく、いくつかのコミュニティへの投稿が含まれています。  具体的な内容は次のとおりです。

* QuantumSimulator ターゲット コンピューターの小規模のシミュレーションと大規模のシミュレーションの両方のパフォーマンスの向上。
* デバッグ機能の改善。
* バグ修正、新しいヘルパー関数、演算および新しいサンプルに関するコミュニティへの投稿。

### <a name="performance-improvements"></a>パフォーマンスの向上

この更新には、すべてのターゲット コンピューターに対する多数および少数の量子ビットのシミュレーションについて、大幅なパフォーマンスの改善が含まれています。  この改善は、Quantum Development Kit の標準サンプルである、H<sub>2</sub> シミュレーションで簡単に確認できます。

### <a name="improved-debugging-functionality"></a>デバッグ機能の改善

この更新では、新しいデバッグ機能が追加されます。
* 2 つの新しい演算 @"microsoft.quantum.extensions.diagnostics.dumpmachine" と @"microsoft.quantum.extensions.diagnostics.dumpregister" を追加しました。これにより、特定の時点でターゲットの量子コンピューターに関する波動関数の情報が出力されます。  
* Visual Studio では、1 つの量子ビットで $\ket{1}$ を測定する確率が、QuantumSimulator ターゲット コンピューターのデバッグ ウィンドウに自動的に表示されるようになりました。
* Visual Studio では **[自動]** と **[ローカル]** のデバッグ ウィンドウでの変数プロパティの表示が改善されました。 

テストとデバッグの詳細については、[こちら](xref:microsoft.quantum.guide.testingdebugging)を参照してください。

### <a name="community-contributions"></a>コミュニティへの投稿

Q#プログラマが成長しているので、お客様がオープンコードベースのライブラリとサンプルを参照していることを嬉しく思いしてい http://github.com/Microsoft/quantum ます。  **皆様のご協力に深く感謝します。** 投稿していただいた方は次のとおりです。
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): 指定された順列を実装する Toffoli ネットワークを構築する、変換ベースの論理合成メソッドを定義するサンプルを投稿しました。 このコードは、関数と操作で完全に記述されてい Q# ます。  [PR #41](https://github.com/Microsoft/Quantum/pull/41)。
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): MICROSOFT MVP Rolf は、 Q# 従来の制御フローと制限されたクォンタム操作を持たない、限られたプログラムのクラスのコードからフラットな qasm コードを生成するサンプルを提供しました。 [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): 制御演算のためのライブラリ関数を提出することにより、コード ベースの向上を支援しました。 [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): @"microsoft.quantum.canon.quantumphaseestimation" を修正し、新しい単体テストを作成しました。  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): QuantumSimulator インスタンスが破棄されていることを確認し、テレポーテーション サンプルをクリーニングしました。 [PR #20](https://github.com/Microsoft/Quantum/pull/20)

さらに、以下の人たちに深く**感謝します**。 商用エンジニアリング サービス チームのこれらの Microsoft ソフトウェア エンジニアは、ハッカソン時にドキュメントに重要な変更を加えた投稿者です。  これらの変更により、私たち全員のわかりやすいオンボード エクスペリエンスが大幅に向上しました。
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>既存のプロジェクトを更新する

このリリースには完全に下位互換性があります。 プロジェクトの nuget パッケージをバージョン `0.2.1806.1503-preview` に単に更新し、**完全な再構築**を行って、すべての中間ファイルが再生成されていることを確認します。

Visual Studio から、[パッケージを更新する](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)方法に関する通常の手順に従います。

コマンド ラインのプロジェクト テンプレートを更新するには、次のコマンドを実行します。
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

このコマンドを実行した後、`dotnet new <project-type> -lang Q#` を使用して作成された新しいすべてのプロジェクトで、このバージョンの Quantum Development Kit が自動的に使用されます。

新しいバージョンを使用するように既存のプロジェクトを更新するには、各プロジェクトのディレクトリ内から次のコマンドを実行します。

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

既存のプロジェクトで単体テストに XUnit 統合も使用する場合は、同様のコマンドを使用して、同じようにそのパッケージを更新することができます。
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

テスト プロジェクトで使用される XUnit のバージョンによっては、XUnit を 2.3.1 に更新することが必要になる場合もあります。
```
dotnet add package xunit -v "2.3.1" 
```

更新後、次のようにして、必ず、以前のバージョンで生成された一時ファイルをすべて削除してください。
```
dotnet clean 
```

### <a name="known-issues"></a>既知の問題

報告する追加の既知の問題はありません。


## <a name="version-0218022202"></a>バージョン 0.2.1802.2202

*リリース日:2018 年 2 月 26 日*

このリリースでは、より多くのプラットフォームでの開発、言語の相互運用性、およびパフォーマンスの強化がサポートされています。 具体的な内容は次のとおりです。

- macOS および Linux ベースの開発のサポート。 
- .NET Core との互換性。これには、プラットフォーム間での Visual Studio Code のサポートが含まれます。
- Quantum Development Kit ライブラリの完全なオープン ソース ライセンス。
- 20 個以上の量子ビットを必要とするプロジェクトでのシミュレーターのパフォーマンスの向上。
- Python 言語 (Windows で使用可能なプレビュー リリース) との相互運用性。

### <a name="net-editions"></a>.NET エディション

.NET プラットフォームは、Windows で提供されている .NET Framework と、Windows、macOS、Linux で使用可能なオープンソースの .NET Core という 2 つの異なるエディションで利用できます。
このリリースでは、Quantum Development Kit のほとんどの部分が、Framework と Core の両方に共通するクラスのセットである、.NET Standard のライブラリとして提供されています。
そのため、これらのライブラリは、.NET Framework または .NET Core の最新バージョンと互換性があります。

したがって、確実に Quantum Development Kit を使用して作成されたプロジェクトを可能な限り移植できるようにするために、Quantum Development Kit を使用して作成されたライブラリ プロジェクトのターゲットを .NET Standard とし、コンソール アプリケーションのターゲットを .NET Core とすることをお勧めします。
Quantum Development Kit の以前のリリースでは .NET Framework のみがサポートされていたため、既存のプロジェクトの移行が必要になる場合があります。これを行う方法の詳細については、以下を参照してください。

### <a name="project-migration"></a>プロジェクトの移行

以前のバージョンの Quantum Development Kit を使用して作成されたプロジェクトは、使用されている NuGet パッケージを更新しない限り、引き続き機能します。 既存のコードを新しいバージョンに移行するには、次の手順を行います。
1. 適切な種類の Q# プロジェクトテンプレート (アプリケーション、ライブラリ、またはテストプロジェクト) を使用して、新しい .Net Core プロジェクトを作成します。
2. 既存の .qs および .cs/.fs ファイルを古いプロジェクトから新しいプロジェクトにコピーします ([追加] > [既存の項目] を使用)。 AssemblyInfo.cs ファイルはコピーしないでください。
3. 新しいプロジェクトをビルドして実行します。

名前空間 Microsoft.Quantum.Canon の演算 RandomWalkPhaseEstimation は、[Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) リポジトリの名前空間 Microsoft.Research.Quantum.RandomWalkPhaseEstimation に移動されたことに注意してください。

### <a name="known-issues"></a>既知の問題

- `--filter`のオプションは、 `dotnet test` で記述されたテストに対して正しく機能しません Q# 。
  そのため、個々の単体テストを Visual Studio Code で実行することはできません。 `dotnet test` すべてのテストを再実行するには、コマンドプロンプトでを使用することをお勧めします。

## <a name="version-0118011707"></a>バージョン 0.1.1801.1707

*リリース日:2018 年 1 月 18 日*

このリリースでは、コミュニティによって報告されたいくつかの問題が修正されます。 つまり、

- シミュレーターは、早期の AVX 対応でない CPU で動作するようになりました。
- 地域10進数の設定では、パーサーが失敗することはありません Q# 。
- `SignD` プリミティブ演算では、`Double`ではなく、`Int` が返されるようになりました。


## <a name="version-011712901"></a>バージョン 0.1.1712.901

*リリース日:2017 年 12 月 11 日*

### <a name="known-issues"></a>既知の問題

#### <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

- Quantum Development Kit に含まれるシミュレーターでは、Microsoft Windows の 64 ビットのインストール版を実行する必要があります。
- Quantum Development Kit と共にインストールされる、Microsoft の量子シミュレーターでは Advanced Vector Extensions (AVX) が利用され、AVX 対応の CPU が必要です。 Q1 2011 (Sandy Bridge) 以降で出荷された Intel プロセッサでは、AVX がサポートされます。 以前の CPU のサポートは評価中であり、詳細について、後日発表する場合があります。

#### <a name="project-creation"></a>プロジェクトの作成

- を使用するソリューション (.sln) を作成する場合、ソリューション Q# はソリューション内の各プロジェクト (.csproj) よりも1つ大きいディレクトリである必要があります。 新しいソリューションを作成する場合は、[新しいプロジェクト] ダイアログボックスの [ソリューションのディレクトリの作成] チェックボックスがオンになっていることを確認することで、これを行うことができます。 これが行われない場合は、Quantum Development Kit の NuGet パッケージを手動でインストールする必要があります。

#### Q#

- Intellisense では、コードに対する適切なエラーは表示されません Q# 。 正しいエラーを確認するには、Visual Studio エラー一覧にビルドエラーが表示されていることを確認してください Q# 。 また、 Q# ビルドが完了するまでエラーが表示されないことにも注意してください。
- 部分アプリケーションで可変配列を使用すると、予期しない動作が発生する可能性があります。
- 不変配列を可変配列にバインドする (a = b にする。この b は可変配列です) 場合、予期しない動作が発生する可能性があります。
- プロファイル、コードカバレッジ、およびその他の VS プラグインは、行をカウントして正確にブロックするとは限りません Q# 。
- コンパイラは、挿入 Q# 文字列を検証しません。 変数名のスペルを間違えたり、挿入文字列で式を使用したりすることにより、C# のコンパイルエラーを作成することができ Q# ます。

#### <a name="simulation"></a>シミュレーション

- 量子シミュレーターでは、OpenMP を使用して、必要な線形代数を並列化します。 既定では、OpenMP で利用可能なすべてのハードウェア スレッドが使用されます。これは、必要な調整を行って実際の作業を小さくするため、多くの場合、少数の量子ビットを含むプログラムの実行速度が低下することを意味します。 これは、環境変数 OMP_NUM_THREADS を小さい数値に設定することによって修正できます。 経験則として、最大 4 つ程度の量子ビットには 1 つのスレッドが適しています。その後、量子ビットごとにスレッドを追加することをお勧めします。ただし、これはアルゴリズムに大きく依存します。

#### <a name="debugging"></a>デバッグ

- F11 (ステップイン) はコードでは機能しません Q# 。
- Q#ブレークポイントまたはシングルステップの一時停止でコード内のコードを強調表示すると、不正確になることがあります。 正しい行が強調表示されても、強調表示が行の不適切な列で開始されて終了する場合があります。

#### <a name="testing"></a>テスト

- テストは64ビットモードで実行する必要があります。 テストが BadImageFormatException で失敗する場合は、[テスト] メニューに移動し、[テストの設定]、[既定のプロセッサ アーキテクチャ]、[X64] の順に選択します。
- テストによっては、実行に時間がかかります (コンピューターによっては、5 分ほどかかる場合があります)。 これは正常な動作です。場合によっては、20 個を超える量子ビットが使用されるため、現在、最大規模のテストは 23 個の量子ビットで実行されています。

#### <a name="samples"></a>サンプル

- 一部のコンピューターでは、環境変数 OMP_NUM_THREADS が "1" に設定されていないと、一部の小さなサンプルの実行速度が低下する場合があります。 「シミュレーション」のリリース ノートも参照してください。

#### <a name="libraries"></a>ライブラリ

- 異なる引数で演算に渡された量子ビットは、すべて別のものであるという暗黙の前提があります。 たとえば、すべてのライブラリ演算 (およびすべてのシミュレーター) では、制御 NOT に渡される 2 つの量子ビットは異なる量子ビットであることが前提となります。 この前提に反すると、予期できない予想外の結果になる可能性があります。 量子コンピューター トレーサー シミュレーターを使用して、これをテストすることができます。
- 場合によっては、Microsoft.Quantum.Bind 関数が期待どおりに動作しないことがあります。
- Microsoft.Quantum.Extensions.Math 名前空間では、SignD 関数で、Int ではなく Double が返されます。ただし、基になる System.Math.Sign 関数では常に整数が返されます。 これらの double はすべて正確なバイナリ表現を持つため、結果を 1.0、-1.0、および 0.0 と比較するのが安全です。
