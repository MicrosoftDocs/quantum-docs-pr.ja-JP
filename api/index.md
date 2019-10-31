---
uid: microsoft.quantum.standardlibsintro
title: Microsoft Quantum の Q# 標準ライブラリ
description: Microsoft Quantum の Q# 標準ライブラリのリファレンス ドキュメント
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999098"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="df42a-103">Q# 標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="df42a-103">Q# standard libraries</span></span> #

<span data-ttu-id="df42a-104">Q# は、Q# *標準ライブラリ*を構成するさまざまな便利な操作、関数、およびユーザー定義型によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df42a-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="df42a-105">Q# 標準ライブラリは、次の 2 つの主要な部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="df42a-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="df42a-106">**準備**: ターゲット コンピューターとコンパイラの一部として定義されている操作と関数。通常は、従来のネイティブ .NET コードです。</span><span class="sxs-lookup"><span data-stu-id="df42a-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="df42a-107">一般的に、各ターゲット コンピューターには各システムに適しているそれぞれ異なる準備の実装があります。</span><span class="sxs-lookup"><span data-stu-id="df42a-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="df42a-108">**規範**: 導入で定義されているロジックに基づいて Q# で定義された操作と関数。</span><span class="sxs-lookup"><span data-stu-id="df42a-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="df42a-109">規範の実装は、ターゲット コンピューターに依存しません。</span><span class="sxs-lookup"><span data-stu-id="df42a-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="df42a-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="df42a-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>