---
title: Microsoft Quantum Development Kit (QDK) のインストール
description: さまざまな環境の Microsoft Quantum Development Kit をインストールする方法。
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 378970dc911ea5a794590f8336ffc6d3f9673285
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867575"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) のインストール

Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)
- 開発を容易にするツール

Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、スタンドアロン アプリケーションとして実行できます。
また、.NET 言語 (通常は C#) または Python で記述されたホスト プログラムと組み合わせて使用することもできます。これにより、従来のプログラム内からクォンタム操作を呼び出すことができます。

これらの各セットアップのワークフローの説明および比較については、「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。

QDK のインストールを続行し、Q# プロジェクトを作成するために、適切なセットアップを選択してください。

[Q# コマンド ライン アプリケーションを使用した開発](xref:microsoft.quantum.install.standalone) - コマンド ラインから Q# を操作する場合は、この方法を選択します。 これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。

[Q# Jupyter Notebook を使用した開発](xref:microsoft.quantum.install.jupyter) - テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。 

[Q# と Python を使用した開発](xref:microsoft.quantum.install.python) - Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成できます。

[Q# と .NET を使用した開発](xref:microsoft.quantum.install.cs) - C#、F#、または VB.NET と Q# を組み合わせて、Q# 操作を呼び出す .NET ホスト プログラムを作成します。
