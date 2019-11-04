---
title: Qubits を使用する |Microsoft Docs
description: Qubits の操作
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183473"
---
# <a name="working-with-qubits"></a>Qubits の操作 #

Q # 言語のさまざまな部分を見てきましたが、それについて説明し、qubits 自体を使用する方法を見てみましょう。

## <a name="allocating-qubits"></a>割り当て (Qubits を) ##

まず、Q # で使用できる qubit を取得するために、`using` ブロック内に qubit を*割り当て*ます。

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

この方法で割り当てられた qubits は、$ \ket{0}$ state; から開始されます。上の例では、`register` は状態が $ \ket{00000} = \ket{0}/otimes \ket{0}/otimes/cドット/otimes \ket{0}$ になります。
`using` ブロックの最後には、そのブロックによって割り当てられたすべての qubits がすぐに割り当て解除され、それ以上使用することはできません。

> [!WARNING]
> ターゲットコンピューターでは、割り当てのために再利用して他の `using` ブロックに提供できるように、割り当て解除の直前に qubits が $ \ket{0}$ 状態にあることを想定しています。
> 可能な場合は常に、ユニタリ操作を使用して、割り当てられた qubits を $ \ket{0}$ に返します。
> 必要に応じて、@"microsoft.quantum.intrinsic.reset" 操作を使用して qubit を測定し、測定結果を使用して、測定された qubit が $ \ket{0}$ に返されるようにすることができます。 このような測定値は、残りの qubits を使用してすべての entangを破棄するため、計算に影響を与える可能性があります。 

## <a name="intrinsic-operations"></a>組み込みの操作 ##

割り当てられた後、qubit を関数と操作に渡すことができます。
ある意味では、これは、実行可能なアクションがすべて操作として定義されているため、Q # プログラムが qubit を使用して実行できることです。
これらの操作については、[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)で詳しく説明しますが、ここでは、qubits との対話に使用できるいくつかの便利な操作について説明します。

1つ目の方法として、1つの $Z $、$Y $、および $ $X、それぞれが型 `Y`を持つ組み込み操作 `X`、`Z`、および `(Qubit => Unit is Adj + Ctl)`によって Q # で表されます。
「組み込みの[操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」で説明されているように、$X $ と `X` はビットフリップ演算または NOT gate と考えることができます。
これにより、いくつかのクラシックビット文字列 $s $: で $ \ket{s_0 s_1 \ ドット s_n} $ という形式の状態を準備できます。

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit 
is Adj + Ctl {

    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> 後で、手動によるフロー制御を必要としない、この操作を記述するよりコンパクトな方法を紹介します。

\Ket transform{0} $ を使用して、$ \ket{+} = \ left (\ket{0} + \ket{1}\ right)//sqrt{2}$ および $ \ket{-} = \ left (\ket{1}-Hadamard{2}-right)//sqrt $H $ などの状態を準備することもできます。: 組み込み操作によって Q # で表される `H : (Qubit => Unit is Adj + Ctl)`:

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {

    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>測定値 ##

組み込みの非インサム演算である `Measure` 操作を使用すると、`Qubit` 型のオブジェクトから古典的な情報を抽出し、その結果として `Result`予約型を持つ古典的な値を結果として割り当てることができます。クォンタムの状態が長くなります。 `Measure` への入力は、Bloch 球の p Li 軸で、型 `Pauli` のオブジェクト (たとえば、`PauliX`) と `Qubit`型のオブジェクトによって表されます。 

単純な例として、$ \ket{0}$ state に1つの qubit を作成し、Hadamard gate ``H`` を適用して、その結果を `PauliZ` ベースで測定する次の操作があります。 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
        H(qubit); 
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator, 
        // we reset the qubit before releasing it. 
        if (result == One) { X(qubit); }   
        // Finally, we return the result of the measurement. 
        return result;
    }
}
```

さらに複雑な例として、次の演算では、`Qubit[]` 型のレジスタ内のすべての qubits が、指定された Pare によって測定された場合は0になり、それ以外の場合は `false` `true` ブール値が返されます。 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Q # 言語では、qubits の測定結果に対する従来の制御フローの依存関係が許可されます。 これにより、では、unitaries を実装するための計算コストを削減できる強力なガジェットを実装できるようになります。 例として、Q # ではいわゆる*繰り返し*呼び出しを簡単に実装できます。これは、基本的なゲートの観点から*予想*低コストを確率論的回線ですが、実際の実行と実際のコストは実際の実行に依存します。さまざまな branchings のインターリーブ。 

Repeat To Success (RU) パターンを容易にするために、Q # はコンストラクトをサポートしています。
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
ここで `statementBlock1` と `statementBlock2` は0個以上の Q # ステートメントであり、`Bool`型の値に評価される有効な式を `expression` します。 一般的なユースケースでは、次の回線は、Bloch 球の $ (I + 2i Z)/\ sqrt{5}$ の無理数軸を中心とした回転を実装します。 これは、既知の RUS パターンを使用して実現されます。 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

この例では、変更可能な変数 `finished` の使用方法を示しています。これは、反復処理までの繰り返しループ全体のスコープ内にあり、ループの前に初期化され、フィックスアップのステップで更新されます。

最後に、"$ \ket{+} $" 状態から開始して、クォンタムの状態を準備する RU パターンの例を示します。これには、(\ sqrt{2}\ket{0}+ \ket{1}-right) $ というクォンタムの{3}{1}状態が用意されています。 [標準ライブラリで提供されている単体テストのサンプル](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs)も参照してください。 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
この操作に示されている注目すべきプログラム機能は、クォンタム操作を伴うループのより複雑な `fixup` 部分です。また、`AssertProb` ステートメントを使用して、プログラム. `Assert` および `AssertProb` ステートメントの詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」も参照してください。 
