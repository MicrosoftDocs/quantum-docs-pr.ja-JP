---
title: 'Microsoft Q # 数値ライブラリの使用'
description: Microsoft Quantum の数値ライブラリで使用できる型と操作について説明します。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ad9f529efd06fdf13bab4467b091aafacf1d5b09
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907258"
---
# <a name="using-the-numerics-library"></a>数値ライブラリの使用

## <a name="overview"></a>概要

数値ライブラリは3つのコンポーネントで構成されています。

1. 整数の加算と比較子を使用した**基本的な整数算術演算**
1. 基本機能の上に構築された**高レベルの整数機能**。これには、乗算、除算、逆転などが含まれます。 符号付き整数と符号なし整数の場合。
1. 固定小数点の初期化、加算、乗算、逆数、多項式評価、および測定を使用した**固定小数点演算機能**。

これらのコンポーネントはすべて、1つの `open` ステートメントを使用してアクセスできます。
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>型

数値ライブラリでは、次の型がサポートされています。

1. **`LittleEndian`** : `qArr[0]` が最下位ビットを表している整数を表す qubit 配列 `qArr : Qubit[]`。
1. **`SignedLittleEndian`** : 2 の補数に格納されている符号付き整数を表す点を除いて、`LittleEndian` と同じです。
1. **`FixedPoint`** : qubit 配列 `qArr2 : Qubit[]` とバイナリポイント位置 `pos`で構成される実数を表します。これは、バイナリポイントの左側にあるバイナリの桁数をカウントします。 `qArr2` は `SignedLittleEndian`と同じ方法で格納されます。

## <a name="operations"></a>運用

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

これらの各操作の詳細と詳細なドキュメントについては、 [docs.microsoft.com](https://docs.microsoft.com/quantum)の Q # ライブラリリファレンスドキュメントを参照してください。

## <a name="sample-integer-addition"></a>サンプル: 整数加算

基本的な例として、$ $ \ket x\ket y\ket x\ket {x + y} $ $ という演算を考えてみます。これは、n-qubit 整数 $x $、n または (n + 1)-qubit レジスタ $y $ を入力として使用し、後者は sum $ (x + y) $ にマップします。 $Y $ が $n $ bit レジスタに格納されている場合は、合計が $ 2 ^ n $ として計算されることに注意してください。

この操作は、Quantum Development Kit を使用して次のように適用できます。
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>サンプル: smooth functions の評価

クォンタム $x コンピューターで $ \ sin (x) $ などの smooth functions を評価するには ($ がクォンタム `FixedPoint` 番号である場合、クォンタム開発キットの数値ライブラリは、操作 `EvaluatePolynomialFxP` と `Evaluate[Even/Odd]PolynomialFxP`を提供します。

1つ目の `EvaluatePolynomialFxP`では、を使用して、$ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \ cドット + a_dx ^ d, $ $ という形式の多項式を評価できます。ここで、$d $ はその*次数*を表します。 これを行うには、必要なのは多項式係数 `[a_0,..., a_d]` (`Double[]`型)、入力 `x : FixedPoint`、および出力 `y : FixedPoint` (最初はゼロ) だけです。
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
結果として $P (x) = 1 + 2x $ が `yFxP`に格納されます。

2番目、`EvaluateEvenPolynomialFxP`、3番目の `EvaluateOddPolynomialFxP`は、それぞれ偶数関数と奇数関数の場合に特に特殊化されています。 つまり、偶数/奇数関数 $f (x) $ および $ $ P_ {偶数} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \ cドット + a_d x ^ {2d}, $ $ $f (x) $ は、_ {偶数} (x) $ または $P _ {奇数} (x): = xcdot P_ {偶数} (x) $ の $P によって、近似されます。
Q # では、次の2つのケースを処理できます。
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
これは $P _ {偶数} (x) = 1 + 2 ^ 2 $、およびを評価します。
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
これは $P _ {奇数} (x) = x + 2x ^ 3 $ と評価されます。

## <a name="more-samples"></a>その他のサンプル

その他のサンプルについては、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を参照してください。

まず、リポジトリを複製し、`Numerics` サブフォルダーを開きます。

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

次に、いずれかのサンプルフォルダーに `cd` し、を使用してサンプルを実行します。

```bash
dotnet run
```
