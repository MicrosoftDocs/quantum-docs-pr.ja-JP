---
title: Microsoft Q# 数値ライブラリの使用
description: Microsoft Quantum の数値ライブラリで使用できる型と操作について説明します。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: dfcb8e9e5a15d0881750d67cf58d7ad47cbecd3a
ms.sourcegitcommit: 897ace8b506adb2331e911ee5633dceced566174
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91764133"
---
# <a name="using-the-numerics-library"></a>数値ライブラリの使用

## <a name="overview"></a>概要

数値ライブラリは3つのコンポーネントで構成されています。

1. 整数の加算と比較子を使用した**基本的な整数算術演算**
1. 基本機能の上に構築された**高レベルの整数機能**。これには、乗算、除算、逆転などが含まれます。 符号付き整数と符号なし整数の場合。
1. 固定小数点の初期化、加算、乗算、逆数、多項式評価、および測定を使用した**固定小数点演算機能**。

これらのコンポーネントはすべて、1つのステートメントを使用してアクセスでき `open` ます。
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>型

数値ライブラリでは、次の型がサポートされています。

1. **`LittleEndian`**: が最 `qArr : Qubit[]` `qArr[0]` 下位ビットを表している整数を表す qubit 配列。
1. **`SignedLittleEndian`**: と同じです `LittleEndian` が、2の補数に格納されている符号付き整数を表している点が異なります。
1. **`FixedPoint`**: Qubit 配列とバイナリポイント位置で構成される実数を表します。この値は、バイナリ `qArr2 : Qubit[]` `pos` ポイントの左側にあるバイナリの桁数をカウントします。 `qArr2` はと同じ方法で格納され `SignedLittleEndian` ます。

## <a name="operations"></a>操作

上記の3種類のそれぞれに対して、さまざまな操作を実行できます。

1. **`LittleEndian`**
    - 加算
    - 比較
    - 乗算
    - 2乗
    - 除算 (剰余あり)

1. **`SignedLittleEndian`**
    - 加算
    - 比較
    - 剰余2の補数を反転する
    - 乗算
    - 2乗

1. **`FixedPoint`**
    - 従来の値への準備/初期化
    - 加算 (古典定数またはその他のクォンタム固定ポイント)
    - 比較
    - 乗算
    - 2乗
    - 偶数関数と奇数関数の特殊化による多項式評価
    - 逆数 (1/x)
    - 測定 (古典 Double)

これらの各操作の詳細と詳細なドキュメントについては、 Q# [docs.microsoft.com](https://docs.microsoft.com/quantum)のライブラリリファレンスドキュメントを参照してください。

## <a name="sample-integer-addition"></a>サンプル: 整数加算

基本的な例として、$ $ \ket x\ket y\ket x\ket {x + y} $ $ という演算を考えてみます。これは、n-qubit 整数 $x $、n または (n + 1)-qubit レジスタ $y $ を入力として使用し、後者は sum $ (x + y) $ にマップします。 $Y $ が $n $ bit レジスタに格納されている場合は、合計が $ 2 ^ n $ として計算されることに注意してください。

この操作は、Quantum Development Kit を使用して次のように適用できます。
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>サンプル: smooth functions の評価

クォンタム $x コンピューターで $ \ sin (x) $ などの smooth functions を評価するには ($ がクォンタム番号である)、 `FixedPoint` クォンタム開発キットの数値ライブラリでは、操作 `EvaluatePolynomialFxP` とを提供し `Evaluate[Even/Odd]PolynomialFxP` ます。

1つ目のは、 `EvaluatePolynomialFxP` $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \ cドット + a_dx ^ d, $ $ という形式の多項式を評価できるようにします。ここで、$d $ は *度*を表します。 これを行うには、必要なのは多項式係数 `[a_0,..., a_d]` (型 `Double[]` )、入力、 `x : FixedPoint` および出力 `y : FixedPoint` (最初はゼロ) だけです。
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
結果として $P (x) = 1 + 2x $ がに格納され `yFxP` ます。

2番目の、 `EvaluateEvenPolynomialFxP` 、および3番目のは、 `EvaluateOddPolynomialFxP` それぞれ偶数と奇数の関数の場合に特殊化されています。 つまり、偶数/奇数関数 $f (x) $ および $ $ P_ {偶数} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \ cドット + a_d x ^ {2d}, $ $ $f (x) $ は、_ {偶数} (x) $ または $P _ {奇数} (x): = xcdot P_ {偶数} (x) $ の $P によって、近似されます。
では、次の Q# 2 つのケースを処理できます。
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
これは $P _ {偶数} (x) = 1 + 2 ^ 2 $、およびを評価します。
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
これは $P _ {奇数} (x) = x + 2x ^ 3 $ と評価されます。

## <a name="more-samples"></a>その他のサンプル

その他のサンプルについては、 [メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を参照してください。

まず、リポジトリを複製し、 `Numerics` サブフォルダーを開きます。

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

次に、の `cd` いずれかのサンプルフォルダーに入力し、を使用してサンプルを実行します。

```bash
dotnet run
```
