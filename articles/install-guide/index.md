---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820710"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) のインストール

Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Python および .NET 言語用 API (つまり、C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)
- 開発を容易にするツール

Q# プログラムは、多くの場合、.NET 言語 (通常 C#) または Python で記述されたホスト プログラムとペアになります。 これにより、従来のプログラム内から量子演算を呼び出すことができます。
さらに、QDK では、Jupyter Notebook と IQ# Jupyter カーネル用に Q# サポートも提供されます。

QDK は、複数の開発環境用に使用できます。 以下のセクションからお好みの設定を選択してください。

- [[Install Q# for C#]\(C# 用 Q# のインストール\):](xref:microsoft.quantum.install.cs) C# と Q# を組み合わせて、Q# 操作を呼び出す C# ホスト プログラムを作成する場合は、この環境を選択します。
- [[Install Q# for Python]\(Python 用 Q# のインストール\):](xref:microsoft.quantum.install.python) Python と Q# を組み合わせて、Q# 操作を呼び出す C# ホスト プログラムを作成する場合は、この環境を選択します。
- [[Install Q# for Jupyter Notebooks]\(Jupyter Notebook 用 Q# のインストール\):](xref:microsoft.quantum.install.jupyter) テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。 Q # と外部の従来のホスト プログラムを組み合わせる場合は、この環境を選択しないでください。
