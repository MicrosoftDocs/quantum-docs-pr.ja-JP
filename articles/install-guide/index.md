---
title: Microsoft Quantum Development Kit (QDK) のインストール
description: さまざまな環境の Microsoft Quantum Development Kit をインストールする方法。
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327571"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) のインストール

Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)
- 開発を容易にするツール

Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、スタンドアロン アプリケーションとして実行できます。

また、.NET 言語 (通常は C#) または Python で記述されたホスト プログラムと組み合わせて使用することもできます。これにより、従来のプログラム内からクォンタム操作を呼び出すことができます。

QDK は、複数の開発環境用に使用できます。 希望するセットアップを選択してください:

[Q# コマンド ライン アプリケーションを使用した開発](xref:microsoft.quantum.install.standalone) - コマンド ラインから Q# を操作する場合は、この方法を選択します。 これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。

[Q# Jupyter Notebook を使用した開発](xref:microsoft.quantum.install.jupyter) - テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。 

[Q# と Python を使用した開発](xref:microsoft.quantum.install.python) - Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成できます。

[Q# と .NET を使用した開発](xref:microsoft.quantum.install.cs) - C#、F#、または VB.NET と Q# を組み合わせて、Q# 操作を呼び出す .NET ホスト プログラムを作成します。
