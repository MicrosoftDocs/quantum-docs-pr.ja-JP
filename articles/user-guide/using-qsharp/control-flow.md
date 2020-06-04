---
title: Q での制御フロー#
description: ループ、条件、その他
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326542"
---
# <a name="control-flow-in-q"></a>Q での制御フロー#

演算または関数内では、最も一般的な命令型の共通言語と同様に、各ステートメントが順番に実行されます。
ただし、この制御フローは、次の3つの方法で変更できます。

- `if`命令
- `for`for
- `repeat`-`until`for

後者については、[後](#repeat-until-success-loop)で説明します。
`if`ただし、および `for` 制御フローの構造は、従来のほとんどのプログラミング言語をよく理解しています。

重要な点として、 `for` ループおよびステートメントは、 `if` 特殊化が自動生成される操作でも使用できます。 この場合、ループの adjoint は方向を反転させ、 `for` 各反復の adjoint を受け取ります。
これは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。
靴を decidedly ている間に、試してみて、お客様の socks を試してみることができます。

## <a name="if-else-if-else"></a>の場合は、それ以外の場合は。それ以外の場合は。

ステートメントでは、 `if` 条件付き実行がサポートされています。
キーワード、 `if` 始めかっこ `(` 、ブール式、右かっこ `)` 、およびステートメントブロック ( _then_ブロック) で構成されます。
この後には、任意の数の else if 句を指定できます。これらは、それぞれキーワード、 `elif` 始めかっこ `(` 、ブール式、右かっこ `)` 、およびステートメントブロック ( _else if_ブロック) で構成されます。
最後に、ステートメントは、キーワードとそれ `else` に続く別のステートメントブロック ( _else_ブロック) で構成される else 句を使用して終了することもできます。

`if`条件が評価され、true の場合は then ブロックが実行されます。
条件が false の場合、最初の else if 条件が評価されます。true の場合は、それ以外の場合は if ブロックが実行されます。
それ以外の場合は、2番目の else-if ブロックがテストされ、3番目以降の場合は、true 条件を持つ句が検出されるか、それ以上の else if 句が存在しなくなるまで続きます。
元の if 条件とすべての else-if 句が false と評価された場合、else ブロックが指定されていると、else ブロックが実行されます。

実行されるブロックはいずれも、それ自体のスコープ内で実行されることに注意してください。
`if`、、またはブロック内で行われたバインディングは、末尾の後には表示され `elif` `else` ません。

たとえば、

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
または
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
ステートメントは、キーワード、 `for` 始めかっこ `(` 、その後に記号または記号の組、キーワード `in` 、型 `Range` または配列の式、右かっこ `)` 、およびステートメントブロックで構成されます。

ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。
範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。
式はループに入る前に完全に評価され、ループの実行中は変更されません。

ループ変数は、ループ本体の各入口でバインドされ、本文の最後にバインド解除されます。
特に、ループ変数は for ループの完了後にバインドされません。
宣言されたシンボルのバインドは不変であり、他の変数バインドと同じ規則に従います。 

例としては、 `qubits` qubits (型) のレジスタを使用する場合があります。 `Qubit[]` 

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
最後に、算術-左2項演算子を使用しました。その詳細については、 `<<<` 「[数値式](xref:microsoft.quantum.guide.expressions#numeric-expressions)」を参照してください。


## <a name="repeat-until-success-loop"></a>繰り返し-成功ループ

Q # 言語を使用すると、古典制御フローは qubits の測定結果に依存することになります。
この機能により、確率論的を実装するためのコンピューティングコストを削減できる強力なガジェットを実装できるようになります。
例として、Q # では、いわゆる*繰り返し-成功*(ru) のパターンを簡単に実装できます。
これらの RU パターンは、基本ゲートの観点から*予想*低コストの確率論的プログラムですが、実際のコストは、考えられるさまざまな branchings の実際の実行と実際のインターリーブによって異なります。

Repeat To Success (RU) パターンを容易にするために、Q # はコンストラクトをサポートしています。

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
条件が true の場合、ステートメントは完了します。それ以外の場合は、fixup が実行され、ループ本体からステートメントが再実行されます。

Repeat/until ループの3つの部分 (本文、テスト、および修正) は、*繰り返しごとに*1 つのスコープとして扱われるので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。
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

このページの下部には、 [ru ループの例](#repeat-until-success-examples)がいくつか含まれています。

> [!TIP]   
> 関数内での繰り返しの成功ループの使用は避けてください。 対応する機能は、関数の while ループによって提供されます。 

## <a name="while-loop"></a>While ループ

繰り返し-成功パターンには、クォンタム固有の connotation があります。 これらは、特定のクラスのクォンタムアルゴリズムで広く使用されているため、Q # の専用言語構成要素です。 ただし、条件に基づいて中断されるループでは、実行の長さがコンパイル時に不明であるため、クォンタムランタイムでは特に注意して処理する必要があります。 一方、関数内での使用は、従来の (非クォンタム) ハードウェアで実行されるコードのみを含むため、問題はありません。 

そのため、Q # では、関数内でのみ while ループを使用できます。 ステートメントは、 `while` キーワード、 `while` 始めかっこ `(` 、条件 (つまり、ブール式)、終わりかっこ `)` 、およびステートメントブロックで構成されます。
ステートメントブロック (ループの本体) は、条件がに評価される限り実行され `true` ます。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return ステートメント

Return ステートメントは、操作または関数の実行を終了し、呼び出し元に値を返します。
これは、キーワードと、 `return` 適切な型の式、および終端のセミコロンで構成されます。

空のタプルを返す呼び出し可能なは、 `()` return ステートメントを必要としません。
早期終了が必要な場合は、 `return ()` この場合はを使用できます。
他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。

操作内に return ステートメントの最大数がありません。
ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。

たとえば、
```qsharp
return 1;
```
or
```qsharp
return ();
```
or
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Fail ステートメント

Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。
これは、キーワードと、その `fail` 後に続く文字列と終端のセミコロンで構成されます。
文字列は、エラーメッセージとしてクラシックドライバーに返されます。

操作内の fail ステートメントの数に制限はありません。
ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。

たとえば、
```qsharp
fail $"Impossible state reached";
```
または、挿入[文字列](xref:microsoft.quantum.guide.expressions#interpolated-strings)を使用します。
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>繰り返し-成功の例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>無理数軸に関する単一の qubit ローテーションの ru パターン 

一般的なユースケースでは、次の Q # 操作は、Bloch 球の $ (I + 2i Z)/\ sqrt $ の無理数軸を中心とした回転を実装し {5} ます。 これは、既知の RUS パターンを使用して実現されます。

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>スコープ内の変更可能な変数を含む RU ループ

この例では、変更可能な変数を使用する方法を示します。この変数は、繰り返しの反復処理の `finished` ループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。

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

### <a name="rus-without-fixup"></a>使用しない RU`fixup`

たとえば、次のコードは、 {5} およびゲートを使用して、確率論的回線を実装する回線であり、重要な回転 $V ゲート (& 3)、(+ 2 i Z)/\ sqrt $ が実装されてい `H` `T` ます。
ループは、平均で $-frac {8} {5} $ 繰り返しで終了します。
詳細については、「繰り返し-成功するまで」を参照してください。これは、[*シングル qubit 2014 Unitaries 非決定的に分解したもの*](https://arxiv.org/abs/1311.1074)です。

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

最後に、"$ \ket{+} $" 状態から始まるクォンタムの状態を準備する RUS パターンの例を示します。この例では、$ \ frac {1} {\ sqrt {3} } \ left (\ sqrt {2} \ket {0} + \ket {1} \ 右) $ が使用されています。
[標準ライブラリで提供されている単体テストのサンプル](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)も参照してください。

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

この操作に示されている重要なプログラム機能は、ループのより複雑な部分です。これには、 `fixup` クォンタム操作が含まれます。また、ステートメントを使用して、 `AssertProb` プログラム内の特定の特定のポイントでクォンタムの状態を測定する確率を確認します。
および操作の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」も参照してください [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。


## <a name="next-steps"></a>次の手順

Q # での[テストとデバッグ](xref:microsoft.quantum.guide.testingdebugging)について説明します。