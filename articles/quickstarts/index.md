---
title: Microsoft Quantum 開発キット (QDK) の設定
description: さまざまな環境に合わせて Microsoft Quantum 開発キットを設定する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870823"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum 開発キット (QDK) の設定

量子プログラミングを開始できるように、お使いの環境に合わせて Microsoft Quantum 開発キット (QDK) を設定する方法について説明します。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)
- 開発を容易にするツール

Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、あるいは Python または .NET 言語 (C#、F#) で作成されたホスト プログラムと組み合わせて、スタンドアロン アプリケーションとして実行できます。 また、[Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/)、または [Docker](#use-the-qdk-with-docker) を使用して、Q# プログラムをオンラインで実行することもできます。 

## <a name="options-for-setting-up-the-qdk"></a>QDK を設定するためのオプション

QDK は、次の 3 つの方法で使用できます。

- [QDK をローカルにインストールする](#install-the-qdk-locally)
- [QDK をオンラインで使用する](#use-the-qdk-online)
- [QDK Docker イメージを使用する](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>QDK をローカルにインストールする

ほとんどの使い慣れた IDE で Q# コードを開発できるだけでなく、Python や .NET (C#、F#) などの他の言語と Q# を統合することもできます。

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 以降)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><b>VS Studio<br>(2019 以降)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebook</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>コマンド ライン</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>OS のサポート:</b></td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">Windows のみ</td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">Windows、macOS、Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# スタンドアロン</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">インストール</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# および Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">インストール</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# および .NET (C#、F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">インストール</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">インストール</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">インストール</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>QDK をオンラインで使用する

また、これらのオプションを使用して、ローカルに何もインストールせずに Q# コードを開発することもできます。

|リソース|長所|制限事項|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|充実したオンライン開発環境  |Azure サブスクリプションとプランが必要 |
|[**Binder**](xref:microsoft.quantum.install.binder) | 無料のオンライン ノートブック エクスペリエンス |永続化なし |

## <a name="use-the-qdk-with-docker"></a>Docker で QDK を使用する

QDK の Docker イメージは、ローカルの Docker イ ンストールで使用することも、ACI など Docker イメージをサポートする任意のサービスを介してクラウドで使用することもできます。

https://github.com/microsoft/iqsharp/#using-iq-as-a-container から IQ# Docker イメージをダウンロードできます。 

Docker を Visual Studio Code リモート開発コンテナーと共に使用して、開発環境を迅速に定義することもできます。 VS Code 開発コンテナーの詳細については、「 https://github.com/microsoft/Quantum/tree/master/.devcontainer 」を参照してください。

## <a name="next-steps"></a>次のステップ

これらの各セットアップのワークフローの説明および比較については、「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。
