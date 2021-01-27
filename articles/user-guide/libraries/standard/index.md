---
title: Microsoft Q# 標準ライブラリの概要
description: 量子プログラムで使用される操作、関数、およびデータ型を定義する Microsoft Q# 標準ライブラリについて説明します。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858310"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# 標準ライブラリの概要

Q# は、Q# "*標準ライブラリ*" を構成するさまざまな便利な操作、関数、およびユーザー定義型によってサポートされています。
[インストールと検証](xref:microsoft.quantum.install)の間にインストールされた [`Microsoft.Quantum.Development.Kit` NuGet パッケージ](https://www.nuget.org/packages/microsoft.quantum.development.kit)により、Q# コンパイラと、ターゲット マシンによって実装される標準ライブラリの一部が提供されます。
[`Microsoft.Quantum.Standard` パッケージ](https://www.nuget.org/packages/microsoft.quantum.standard)には、ターゲット マシン間で移植可能な Q# 標準ライブラリの一部が用意されています。

Q# 標準ライブラリによって定義されたシンボルは、[API ドキュメント](xref:microsoft.quantum.apiref-intro)ではるかに詳細に定義されています。

以下のセクションでは、標準ライブラリの各部分の最も顕著な特徴について説明し、各機能が実際にどのように使用されるかについていくつかのコンテキストを示します。
