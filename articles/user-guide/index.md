---
title: Q# ユーザー ガイド
description: ユーザー ガイドの目的と内容の概要
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869632"
---
# <a name="the-no-locq-user-guide"></a>Q# ユーザー ガイド

Q# ユーザー ガイドへようこそ。 

このガイドの様々なトピックでは、Q# 言語の主要概念と、量子プログラムを記述するために必要なすべての情報について説明します。

## <a name="user-guide-contents"></a>ユーザー ガイドの内容

- [Q# の基本](xref:microsoft.quantum.guide.basics):Q# プログラミング言語の目的と機能に関する概要について説明します。 

- [Q# プログラム実行する方法](xref:microsoft.quantum.guide.host-programs): Q# プログラムの実行方法について説明します。また、コマンド ライン、Q# Jupyter Notebook、または Python や .NET 言語で記述された従来のホスト プログラムから、プログラムを呼び出すためのさまざまな方法の概要を示します。

### <a name="no-locq-language"></a>Q# 言語

- [Q#の型](xref:microsoft.quantum.guide.types):Q# の型モデルを紹介し、型を指定して操作するための構文について説明します。

- [型式](xref:microsoft.quantum.guide.expressions):Q# の各型の値の指定、参照、結合、および操作を行う方法について詳しく説明します。 

### <a name="using-no-locq"></a>Q# の使用

- [Q# のファイル構造](xref:microsoft.quantum.guide.filestructure):`*.qs` Q# ファイルの構造と構文について説明します。

- [演算と関数](xref:microsoft.quantum.guide.operationsfunctions):Q# 言語の 2 つの呼び出し可能な型について詳しく説明します。すなわち、"*演算*" (量子ビット レジスタに対するアクションを含みます) と "*関数*" (従来の情報と厳密に連携して機能します) です。 
    ここでは、adjoint および制御されたバージョンの量子操作を含め、これらを定義して呼び出す方法について説明します。

- [変数](xref:microsoft.quantum.guide.variables): Q# プログラム内における変数の役割と、それらを効果的に活用する方法について説明します。 
    たとえば、バインド スコープに関する情報に加えて、変更できない変数と変更可能な変数の違い、およびそれらを割り当てまたは再割り当てする方法についても説明します。

- [量子ビットの操作](xref:microsoft.quantum.guide.qubits):個々の量子ビットと量子ビットの系を扱うために使用する Q# の機能について説明します。具体的には、それらの割り当て、それらに対する演算の実行、それらの測定です。 

- [制御フロー](xref:microsoft.quantum.guide.controlflow):Q# で使用できるプログラミング制御フロー パターンについて詳しく説明します。これには、多くの標準的な手法 (条件付き実行、for ループ、while ループなど) に加え、量子固有の "成功するまで繰り返す" パターンが含まれます。

- [テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging):自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。 
    量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。 
    さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。 これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。 
    その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: [量子複製不可能定理](xref:microsoft.quantum.concepts.pauli))。

### <a name="quantum-simulators-and-resource-estimators"></a>量子シミュレーターとリソース エスティメーター

- [量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines):使用可能なさまざまなシミュレーターの概要と、ホスト プログラムとターゲット コンピューター間の一般的な実行モデル。

- [完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator):完全な量子状態をシミュレートするターゲット コンピューター。 小規模のプログラムを完全に実行またはデバッグする場合に便利です (数十の量子ビット未満)。

- [リソース エスティメーター](xref:microsoft.quantum.machines.resources-estimator):量子コンピューターで Q# 演算の特定のインスタンスを実行するために必要なリソースを推定します。

- [トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro):量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。そのため、数千もの量子ビットを使用する量子プログラムを実行できます。 量子プログラム内のクラシック コードをデバッグする場合や、必要なリソースを推定する場合に便利です。

- [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator):特別な用途のための量子シミュレーターで、数百万の量子ビットで使用できますが、限定された量子演算のセット (X、CNOT、およびマルチ制御 X) を使用するプログラムに対してのみ使用できます。

### <a name="quick-reference-pages"></a>クイック リファレンス ページ

- [IQ# マジック コマンド](xref:microsoft.quantum.guide.quickref.iqsharp):Q# Jupyter Notebook 内の IQ# マジック コマンドのクイック リファレンス ページ。
