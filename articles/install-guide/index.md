---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
description: C#、Python、および Jupyter Notebook 環境用の Microsoft Quantum 開発キットのインストール方法。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680188"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) のインストール

Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)
- 開発を容易にするツール

Q# プログラムは、多くの場合、.NET 言語 (通常 C#) または Python で記述されたホスト プログラムとペアになります。 これにより、従来のプログラム内から量子演算を呼び出すことができます。
さらに、QDK では、Jupyter Notebook と IQ# Jupyter カーネル用に Q# サポートも提供されます。

QDK は、複数の開発環境用に使用できます。 以下のセクションからお好みの設定を選択してください。

- [Q# コマンド ライン アプリケーション:](xref:microsoft.quantum.install.standalone) コマンド ラインから Q# を操作する場合は、この方法を選択します。 これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。
- [[Install Q# for Jupyter Notebooks]\(Jupyter Notebook 用 Q# のインストール\):](xref:microsoft.quantum.install.jupyter) テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。 
- [Q# と Python を使用した開発:](xref:microsoft.quantum.install.python) Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成する場合。
- [Q# と C# または F# を使用した開発:](xref:microsoft.quantum.install.cs) C# または F# と Q# を組み合わせて Q# 操作を呼び出す .NET ホスト プログラムを作成する場合。
