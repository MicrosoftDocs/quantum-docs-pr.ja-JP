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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834484"
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

|&nbsp; | **VS Code<br> (2019 以降)**| **Visual Studio<br> (2019 以降)** | **Jupyter Notebook** | **コマンド ライン**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**OS** |Windows、macOS、Linux |Windows のみ |Windows、macOS、Linux |Windows、macOS、Linux |
|<br>**Q# スタンドアロン** |<br>[インストール](xref:microsoft.quantum.install.standalone) |<br> [インストール](xref:microsoft.quantum.install.standalone)  |<br> [インストール](xref:microsoft.quantum.install.jupyter) |<br>[インストール](xref:microsoft.quantum.install.standalone)|
|**Q#  および Python** |[インストール](xref:microsoft.quantum.install.python) |[インストール](xref:microsoft.quantum.install.python) |[インストール](xref:microsoft.quantum.install.jupyter) |[インストール](xref:microsoft.quantum.install.python) |
|**Q# および .NET (C#、F#)**|[インストール](xref:microsoft.quantum.install.cs) |[インストール](xref:microsoft.quantum.install.cs)|&#10006; |[インストール](xref:microsoft.quantum.install.cs) |

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
