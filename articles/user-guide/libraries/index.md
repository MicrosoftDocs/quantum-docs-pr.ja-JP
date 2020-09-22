---
title: Quantum 開発キット ライブラリ
description: Microsoft Quantum 開発キットに含まれる標準、化学、数値の各ライブラリの概要。
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835725"
---
# <a name="overview-of-no-locq-libraries"></a>Q# ライブラリの概要
Quantum 開発キットには、Q# で量子アプリケーションを簡単に開発するためのいくつかのライブラリが用意されています。
ドキュメントのこのセクションでは、そのライブラリと、それらをプログラムで使用する方法について説明します。

- [**標準ライブラリ**](xref:microsoft.quantum.libraries.standard.intro): このセクションでは、Q# のプログラムとターゲット コンピューターの間のインターフェイスを定義する導入部、規範、Q# のプログラムの記述で使用する汎用的な操作と関数を提供する Q# ライブラリについて説明します。
- [**量子化学ライブラリ**](xref:microsoft.quantum.chemistry.concepts.intro): このセクションでは、量子化学ライブラリについて説明します。このライブラリは、フェルミオンのハミルトニアンの表記を読み込むデータ モデルと、その表記に作用する量子シミュレーションの操作と関数を提供します。
- [**量子数値ライブラリ**](xref:microsoft.quantum.numerics.intro): このセクションでは、数学関数のホストに対する実装を提供する、量子数値ライブラリについて説明します。 整数 (符号付きと符号なし) と固定小数点表記がサポートされています。
- [**量子機械学習ライブラリ**](xref:microsoft.quantum.machine-learning.concepts.intro):このセクションでは、量子機械学習ライブラリについて説明します。これは、量子コンピューティングを利用してデータを理解するためのシーケンシャル分類器の実装を提供します。

ライブラリのソースとコード サンプルは、GitHub から入手できます。
詳細については、[ライセンス](xref:microsoft.quantum.libraries.licensing)を参照してください。 ライブラリについては、パッケージ参照 ("バイナリ") も使用でき、プロジェクトにライブラリを含めるための別の手段が用意されています。
これを取得するには [NuGet](https://nuget.org) を使用すると便利です。
