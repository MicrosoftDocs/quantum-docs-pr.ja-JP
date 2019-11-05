---
title: Quantum 開発キット ライブラリ | Microsoft Docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 7b51945a8aaf937856441cdb10e8a024bf816f88
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442433"
---
# <a name="overview-of-q-libraries"></a>Q# ライブラリの概要
Quantum 開発キットには、Q# で量子アプリケーションを簡単に開発するためのいくつかのライブラリが用意されています。
ドキュメントのこのセクションでは、そのライブラリと、それらをプログラムで使用する方法について説明します。

- [**標準ライブラリ**](xref:microsoft.quantum.libraries.standard.intro): このセクションでは、Q# のプログラムとターゲット コンピューターの間のインターフェイスを定義する導入部、規範、Q# のプログラムの記述で使用する汎用的な操作と関数を提供する Q# ライブラリについて説明します。
- [**量子化学ライブラリ**](xref:microsoft.quantum.chemistry.concepts.intro): このセクションでは、量子化学ライブラリについて説明します。このライブラリは、フェルミオンのハミルトニアンの表記を読み込むデータ モデルと、その表記に作用する量子シミュレーションの操作と関数を提供します。
- [**量子数値ライブラリ**](xref:microsoft.quantum.numerics.intro): このセクションでは、数学関数のホストに対する実装を提供する、量子数値ライブラリについて説明します。 整数 (符号付きと符号なし) と固定小数点表記がサポートされています。

ライブラリのソースとコード サンプルは、GitHub から入手できます。 詳細については、「[licensing](xref:microsoft.quantum.libraries.licensing)」(ライセンス) のセクションも参照してください。 プロジェクトにライブラリを追加する別の方法を提供するライブラリについては、パッケージ参照 ("バイナリ") も使用できます。 これを取得するには [NuGet](https://nuget.org) を使用すると便利です。  