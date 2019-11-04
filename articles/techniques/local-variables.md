---
title: 'Q # の手法-ローカル変数 |Microsoft Docs'
description: 'Q # の手法-ローカル変数'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183286"
---
# <a name="local-variables"></a>ローカル変数 #

Q # の任意の型の値を変数に代入して、`let` キーワードを使用して操作または関数内で再利用することができます。
その例をご紹介します。

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

これにより、`measurementOperator`と呼ばれる変数に、特定の一連の P# li 演算子が割り当てられます。

> [!TIP]
> `let` ステートメントの右辺の式は明確で、型はコンパイラによって推論されるため、新しい変数の型を明示的に指定する必要がないことに注意してください。 

Q # の変数は*変更*できません。つまり、変数がこのように定義されると、どのような方法でも変更することはできなくなります。
これにより、操作の `Adjoint` バリアントを適用するために、変数に対して動作する古典的なロジックの最適化など、いくつかの有益な最適化を行うことができます。

上記の `let` バインディングを使用して定義された変数は、操作の本体や `for` ループの内容など、特定のスコープに対してローカルです。


## <a name="mutability"></a>可能性 ##

`let`で変数を作成する代わりに、`mutable` キーワードを使用して、`set` キーワードを使用して最初に作成した後に再バインドできる特別な変更可能な変数を作成します。

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Q # のすべての型 (配列を含む) は、値のセマンティクスに従います。 特に、配列項目を更新することはできません。 既存の配列を変更するには、のレコードの場合と同じように、コピーと更新F#のメカニズムを利用する必要があります。 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)に用意されている配列にライブラリツールを使用すると、たとえば、インデックス `i` の PPaulis li が指定された値を取得し、その他のすべてのエントリが id である、などの配列を返す関数を簡単に定義できます。 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

ここでは、Q # のステートメントと式について説明するときに、配列の操作方法について詳しく説明します。 

Q # 内の可変性は、型または値ではなく*シンボル*に適用される概念です。 具体的には、型システム内の表現が暗黙的または明示的に指定されておらず、バインディングが変更可能かどうか (`mutable` キーワードによって示されます)、または (`let`によって示されるように) 不変であるかどうかは、バインドされた変数の型を変更しません。 これは、特殊な関数と操作の中で、可能性を分離するための重要な方法を提供します。
特に、変更可能な変数を使用する操作に対する adjoint の特殊化が自動生成されない場合でも、自動生成は、変更性を使用する関数を呼び出す操作に対しては正常に機能します。
このため、可能な限り短い変更性を使用する関数と操作を作成することをお勧めします。これにより、残りのクォンタムプログラムは、通常の不変変数を使用して書き込むことができます。


## <a name="deconstruction"></a>分解 ##

1つの変数を割り当てるだけでなく、`let` キーワードと `mutable` キーワード (実際にはその他のバインドコンストラクト) を割り当てることに加えて、[タプル型](xref:microsoft.quantum.language.type-model#tuple-types)の内容を展開することもできます。
このフォームの割り当ては、そのタプルの要素を*分解*と言います。
たとえば、タプルによって Hamiltonian 内の用語をモデル化する場合、分解を使用して、その用語でシミュレートする必要があるさまざまなデータにアクセスできます。

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


