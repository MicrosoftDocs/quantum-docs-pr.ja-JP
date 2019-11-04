---
title: 量子数値ライブラリの概要 | Microsoft Docs
description: 量子数値ライブラリの概要
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442437"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>量子数値ライブラリの概要

多くの量子アルゴリズムは、入力の重ね合わせに対して数学関数を評価する[オラクル](xref:microsoft.quantum.concepts.oracles)に依存しています。
たとえば、Shor のアルゴリズムの主要なコンポーネントは、固定 $a$ に対して $f(x) = a^x\operatorname{mod} N$ を、数値を因数 $N$ に対して、$x$ a $2n$-qubit 整数を均一の重ね合わせですべての $2n$-bit 文字列に対して、評価します。

実際の量子コンピューターで Shor のアルゴリズムを実行するには、ターゲット マシンのネイティブ操作に関してこの関数を記述する必要があります。
最下位ビットから数えて $i$ 番目のビットを示す $x_i$ とともに $x$ のバイナリ表現を使用すると、$f(x)$ は $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$ として記述できます。
次に、これは項 $a^{2^i x_i}=(a^{2^i})^{x_i}$ の積 (mod N) として記述できます。 したがって、関数 $f(x)$ は、$x_i$ がゼロ以外であることを条件として 2n$ (モジュラー) の $a^{2^i}$ による乗算の連続を使用して実装できます。 定数 $a^{2^i}$ はアルゴリズムの実行前に事前計算し剰余 N を減らすことができます。

この一連の制御されたモジュラー乗算は、さらに簡略化できます。各乗算は $n$ 制御されたモジュラー加算のシーケンスを使用して実行できます。また、各モジュラー加算は、通常の加算と比較基準から構築できます。


実際の実装に到達するために多くの手順が必要なので、最初からこのような機能を使用できるようにすると非常に便利です。
このため、Quantum Development Kit では、さまざまな数値の機能がサポートされています。


## <a name="functionality"></a>機能

これまでに説明した整数演算以外にも、数値ライブラリでは次の機能が提供されています。

 - 1 つまたは 2 つの量子整数値を入力として使用する、符号付き (符号なし) 整数の機能 (乗算、平方、剰余がある除算、反転、...)
 - 1 つまたは 2 つの量子固定小数点数を入力として持つ、固定小数点機能 (加算/減算、乗算、平方、1/x、多項式評価)

## <a name="getting-started"></a>使用の開始

数値ライブラリの使用を開始するには、[インストール ガイド](xref:microsoft.quantum.numerics.installation)を参照してください。また、[数値ライブラリの使用](xref:microsoft.quantum.numerics.usage)に関するさらに詳しい情報を確認してください。
