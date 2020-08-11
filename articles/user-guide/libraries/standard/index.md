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
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="5fdf5-103">Q# 標準ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="5fdf5-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="5fdf5-104">Q# は、Q# "*標準ライブラリ*" を構成するさまざまな便利な操作、関数、およびユーザー定義型によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5fdf5-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="5fdf5-105">[インストールと検証](xref:microsoft.quantum.install)の間にインストールされた [`Microsoft.Quantum.Development.Kit` NuGet パッケージ](https://www.nuget.org/packages/microsoft.quantum.development.kit)により、Q# コンパイラと、ターゲット マシンによって実装される標準ライブラリの一部が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5fdf5-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="5fdf5-106">[`Microsoft.Quantum.Standard` パッケージ](https://www.nuget.org/packages/microsoft.quantum.standard)には、ターゲット マシン間で移植可能な Q# 標準ライブラリの一部が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5fdf5-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="5fdf5-107">Q# 標準ライブラリによって定義されたシンボルは、[API ドキュメント](xref:microsoft.quantum.standardlibsintro)ではるかに詳細に定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fdf5-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="5fdf5-108">以下のセクションでは、標準ライブラリの各部分の最も顕著な特徴について説明し、各機能が実際にどのように使用されるかについていくつかのコンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="5fdf5-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
