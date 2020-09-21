---
title: 制御フロー Q#
description: ループ、条件、その他
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833514"
---
# <a name="control-flow-in-no-locq"></a>制御フロー Q#

演算または関数内では、各ステートメントが順序どおりに実行されます。これは、その他の一般的な従来の言語と似ています。
ただし、制御フローを変更するには、次の3つの方法があります。

* `if` ステートメント
* `for` for
* `repeat-until-success` for
* 活用 ( `apply-within` ステートメント)

`if`および `for` 制御フローの構造は、ほとんどの一般的なプログラミング言語に慣れています。 [`Repeat-until-success`](#repeat-until-success-loop) ループと [活用](#conjugations) については、この記事の後半で説明します。

重要な点として、 `for` ループおよびステートメントは、 `if` [特殊化](xref:microsoft.quantum.guide.operationsfunctions) が自動生成される操作で使用できます。 このシナリオでは、ループの adjoint が方向を反転させ、 `for` 各反復の adjoint を取得します。
このアクションは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。 

## <a name="if-else-if-else"></a>の場合は、それ以外の場合は。それ以外の場合は。

ステートメントでは、 `if` 条件付き処理がサポートされています。
キーワード、 `if` かっこで囲まれたブール式、およびステートメントブロック ( _then_ ブロック) で構成されます。
必要に応じて、任意の数の else 句を使用できます。各句は、キーワード、 `elif` かっこで囲まれたブール式、およびステートメントブロック ( _else_ ブロック) で構成されます。
最後に、ステートメントは、キーワードとそれ `else` に続く別のステートメントブロック ( _else_ ブロック) で構成される else 句を使用して終了することもできます。

`if`条件が評価され、 *true*の場合は*then*ブロックが実行されます。
条件が *false*の場合、最初の else if 条件が評価されます。true の場合は、 *else if* ブロックが実行されます。
それ以外の場合は、2番目の else-if ブロックが評価され、次に3番目のは、true 条件を持つ句が検出されるか、それ以上 else if 句が存在しなくなるまで続きます。
元の *if* 条件とすべての else-if 句が *false*と評価された場合、 *else* ブロックが実行されます (指定されている場合)。

いずれかのブロックが実行されると、それ自体のスコープ内で実行されることに注意してください。
`if`、 `elif` 、またはブロック内で行われたバインディングは、ブロックの終了後には `else` 参照できません。

たとえば、次のように入力します。

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
or
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>For ループ

`for`ステートメントでは、整数範囲または配列に対する反復処理がサポートされています。
ステートメントは、キーワードと、 `for` その後にシンボルまたは記号の組、キーワード、 `in` 型 `Range` または配列の式、すべてのかっこ内、およびステートメントブロックで構成されます。

ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。
範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。
式はループに入る前に完全に評価され、ループの実行中は変更されません。

ループ変数は、ループ本体への各入り口でバインドされ、本文の末尾でバインド解除されます。
ループ変数は、for ループの完了後にバインドされません。
ループ変数のバインドは不変であり、他の変数バインドと同じ規則に従います。 

これらの例で `qubits` は、は qubits (型) のレジスタです。 `Qubit[]` 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

最後に、算術シフト左の二項演算子のを使用して `<<<` います。 詳細については、「 [数値式](xref:microsoft.quantum.guide.expressions#numeric-expressions)」を参照してください。

## <a name="repeat-until-success-loop"></a>繰り返し-成功ループ

この言語では、 Q# 古典制御フローは qubits の測定結果に依存します。
さらに、この機能により、unitaries を実装するための計算コストを削減できる強力なガジェットを実装できるようになります。
この例として、の *繰り返しの成功* (ru) パターンが挙げられ Q# ます。
これらの RU パターンは、基本的なゲートの観点から、 *予想* 低コストの確率論的プログラムです。発生したコストは、実際の実行と、考えられる複数の branchings のインターリーブによって異なります。

繰り返し-成功 (RU) パターンを容易にするために、は Q# コンストラクトをサポートしています。

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

ここで `expression` 、は型の値に評価される有効な式です `Bool` 。
ループの本体が実行され、条件が評価されます。
条件が true の場合、ステートメントは完了します。それ以外の場合は、フィックスアップが実行され、ステートメントがループ本体から開始され、再度実行されます。

RUS ループの3つの部分 (本文、テスト、および修正) は、 *繰り返しごとに*1 つのスコープとして扱われるので、本文にバインドされているシンボルはテストと修正の両方で使用できます。
ただし、修正の実行を完了すると、ステートメントのスコープが終了します。これにより、本体またはフィックスアップ中に作成されたシンボルバインドは、後続の繰り返しでは使用できなくなります。

さらに、 `fixup` 多くの場合、ステートメントは便利ですが、必ずしも必要ではありません。
必要でない場合、コンストラクト

```qsharp
repeat {
    // do stuff
}
until (expression);
```

は、有効な RUS パターンでもあります。

その他の例と詳細については、この記事の「 [繰り返し-成功の例](#repeat-until-success-examples) 」を参照してください。

> [!TIP]   
> 関数内での繰り返しの成功ループの使用は避けてください。 *While*ループを使用して、関数内で対応する機能を提供します。 

## <a name="while-loop"></a>while ループ

繰り返し-成功パターンには、クォンタム固有の connotation があります。 これらは、クォンタムアルゴリズムの特定のクラスで広く使用されているため、の専用言語構成要素 Q# です。 ただし、条件に基づいて中断されるループは、実行の長さがコンパイル時に不明であるため、クォンタムのランタイムでは特に注意して処理されます。 ただし、これらのループには従来の (非クォンタム) ハードウェアで実行されるコードのみが含まれているため、関数内での使用は問題ありません。 

Q#したがって、では、関数内でのみ while ループを使用できます。
ステートメントは、 `while` キーワード、 `while` かっこで囲まれたブール式、およびステートメントブロックで構成されます。
ステートメントブロック (ループの本体) は、条件がと評価されている限り実行され `true` ます。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>活用

従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。 これらの効果は、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。 クォンタムコンピューティングの一般的なパターンは次のようになります。 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

Q# では、前の変換を実装する活用形ステートメントがサポートされています。 このステートメントを使用すると、 `ApplyWith` 次のように操作を実装できます。

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
このような活用形ステートメントは、外部および内部の変換を操作として簡単に使用できない場合に便利ですが、複数のステートメントで構成されるブロックで記述する方が便利です。 

内部ブロックで定義されているステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。
内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。 

## <a name="return-statement"></a>Return ステートメント

Return ステートメントは、操作または関数の実行を終了し、値を呼び出し元に返します。
これは、キーワードと、 `return` 適切な型の式、および終端のセミコロンで構成されます。

たとえば、次のように入力します。
```qsharp
return 1;
```
or
```qsharp
return (results, qubits);
```

* 空のタプルを返す呼び出し可能なは、 `()` return ステートメントを必要としません。
* 操作または関数からの早期終了を指定するには、を使用し `return ();` ます。
他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。
* 操作内に return ステートメントの最大数がありません。
ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。

   
## <a name="fail-statement"></a>Fail ステートメント

Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。
これは、キーワードと、その `fail` 後に続く文字列と終端のセミコロンで構成されます。
このステートメントは、文字列をエラーメッセージとしてクラシックドライバーに返します。

操作内の fail ステートメントの数に制限はありません。
ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。

たとえば、次のように入力します。

```qsharp
fail $"Impossible state reached";
```
または、挿入 [文字列](xref:microsoft.quantum.guide.expressions#interpolated-strings)を使用します。
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>繰り返し-成功の例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>無理数軸についてのシングル qubit ローテーションの ru パターン 

一般的なユースケースでは、次の操作によって、 Q# Bloch 球の $ (I + 2i Z)/\ sqrt $ の無理数軸の周りの回転が実装され {5} ます。 実装では、既知の RUS パターンを使用します。

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>スコープ内の変更可能な変数を使用した RU ループ

この例では、変更可能な変数を使用する方法を示します。この変数は、反復可能な反復処理の `finished` ループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>使用しない RU `fixup`

この例では、修正手順のない RUS ループを示します。 このコードは、 {5} およびゲートを使用して、確率論的回線で重要な回転ゲート $V (& a) = (\ bold 終了 + 2 i Z)/\ sqrt $ を実装し `H` `T` ます。
ループは、平均で $-frac {8} {5} $ 繰り返しで終了します。
詳細については、「繰り返し-成功するまで」を参照してください。これは、 [*シングル qubit 2014 Unitaries 非決定的に分解したもの*](https://arxiv.org/abs/1311.1074) です。

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>クォンタムの状態を準備する RU

最後に、"$ \ket{+} $" 状態から始まるクォンタムの状態を準備する RUS パターンの例を次に示します。この例では、"$ \ frac {1} {\ sqrt {3} } \ left (\ sqrt {2} \ket {0} + \ket {1} \ right) $" となります。

この操作に示されている重要なプログラム機能は次のとおりです。

* ループのより複雑な `fixup` 部分。これには、クォンタム操作が含まれます。 
* ステートメントを使用して、 `AssertMeasurementProbability` プログラム内の指定した特定のポイントでクォンタムの状態を測定する確率を確認します。

操作と操作の詳細につい [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ては、「 [テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」を参照してください。

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

詳細については、次を参照してください。 [標準ライブラリに用意されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)です。

## <a name="next-steps"></a>次のステップ

での [テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging) について説明 Q# します。
