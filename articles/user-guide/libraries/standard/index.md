---
title: Microsoft Q# 標準ライブラリの概要
description: 量子プログラムで使用される操作、関数、およびデータ型を定義する Microsoft Q# 標準ライブラリについて説明します。
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868476"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# 標準ライブラリの概要

Q# は、Q# "*標準ライブラリ*" を構成するさまざまな便利な操作、関数、およびユーザー定義型によってサポートされています。
[インストールと検証](xref:microsoft.quantum.install)の間にインストールされた [`Microsoft.Quantum.Development.Kit` NuGet パッケージ](https://www.nuget.org/packages/microsoft.quantum.development.kit)により、Q# コンパイラと、ターゲット マシンによって実装される標準ライブラリの一部が提供されます。
[`Microsoft.Quantum.Standard` パッケージ](https://www.nuget.org/packages/microsoft.quantum.standard)には、ターゲット マシン間で移植可能な Q# 標準ライブラリの一部が用意されています。

Q# 標準ライブラリによって定義されたシンボルは、[API ドキュメント](xref:microsoft.quantum.standardlibsintro)ではるかに詳細に定義されています。

以下のセクションでは、標準ライブラリの各部分の最も顕著な特徴について説明し、各機能が実際にどのように使用されるかについていくつかのコンテキストを示します。
