---
title: Q# ユーザー ガイド
description: ユーザー ガイドの目的と内容の概要
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231759"
---
# <a name="the-no-locq-user-guide"></a>Q# ユーザー ガイド

Q# ユーザー ガイドへようこそ。 

このガイドのさまざまなトピックでは、Q#を使用して、量子プログラムを開発するための基本事項をいくつか紹介します。

Q# 量子プログラミング言語の完全な仕様とドキュメントについては、[Q# 言語ガイド](xref:microsoft.quantum.qsharp.index)を参照します。 

## <a name="user-guide-contents"></a>ユーザー ガイドの内容

- [Q# プログラム](xref:microsoft.quantum.guide.programs):Q# での量子プログラムの概要について説明します。 

- [Q# プログラム実行する方法](xref:microsoft.quantum.guide.host-programs): Q# プログラムの実行方法について説明します。また、コマンド ライン、Q# Jupyter Notebook、または Python や .NET 言語で記述された従来のホスト プログラムから、プログラムを呼び出すためのさまざまな方法の概要を示します。

- [テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging):自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。 
    量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。 
    さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。 これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。 
    その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: [量子複製不可能定理](xref:microsoft.quantum.concepts.pauli))。

### <a name="quantum-simulators-and-resource-estimators"></a>量子シミュレーターとリソース エスティメーター

- [量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines):使用可能なさまざまなシミュレーターの概要と、ホスト プログラムとターゲット マシンを連携させて Q# プログラムを実行する方法。

- [完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator):完全な量子状態をシミュレートするターゲット コンピューター。 小規模のプログラムを完全に実行またはデバッグする場合に便利です (数十の量子ビット未満)。

- [リソース エスティメーター](xref:microsoft.quantum.machines.resources-estimator):量子コンピューターで Q# 演算の特定のインスタンスを実行するために必要なリソースを推定します。

- [トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro):量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。そのため、数千もの量子ビットを使用する量子プログラムを実行できます。 量子プログラム内のクラシック コードをデバッグする場合や、必要なリソースを推定する場合に便利です。

- [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator):特別な用途のための量子シミュレーターで、数百万の量子ビットで使用できますが、限定された量子演算のセット (X、CNOT、およびマルチ制御 X) を使用するプログラムに対してのみ使用できます。

### <a name="quick-reference-pages"></a>クイック リファレンス ページ

- [IQ# マジック コマンド](xref:microsoft.quantum.guide.quickref.iqsharp):Q# Jupyter Notebook 内の IQ# マジック コマンドのクイック リファレンス ページ。
