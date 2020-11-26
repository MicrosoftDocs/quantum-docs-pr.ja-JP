---
title: 'Q # Introdution'
description: 「」の「クォンタムプログラムの概要」#
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233977"
---
# <a name="q-quantum-programming-language"></a>Q # クォンタムプログラミング言語

Q # プログラミング言語について理解しておく必要があるものはすべて、 [q # 言語ガイド](xref:microsoft.quantum.qsharp.index)で詳しく説明されています。 他の [言語の設計プロセス](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) と同様に、microsoft はオープンソースであり、投稿を歓迎しています。
Q # の背後にある基礎と動機の背景については、「 [q # が必要な理由](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)」を参照してください。  
Q # は、簡単な概要については、「Quantum Development Kit (QDK)」の一部として出荷されています。 [QDK](xref:microsoft.quantum.overview.q-sharp)の概要については、こちらをご覧ください。 

## <a name="what-is-a-quantum-program"></a>クォンタムプログラムとは

クォンタムプログラムは、クォンタムシステムと対話することによって計算を実行する、特定の一連の従来のサブルーチンとして表示されます。Q # で記述されたプログラムは、クォンタム状態を直接モデル化するのではなく、従来のコントロールコンピューターが qubits とどのようにやり取りするかを説明します。
これにより、各ターゲットコンピューター上でもクォンタムの状態を完全には認識できなくなります。これは、コンピューターによって *は* 、解釈が異なる場合があります。 

重要なのは、Q # では、量子機構の qubit またはその他のプロパティの状態を直接 introspect ことができないことです。これにより、実際には、1つのコンピューターで Q # プログラムが物理的に実行されることが保証されます。
代わりに、プログラムはなどの操作を呼び出して、 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) qubit から古典情報を抽出できます。

割り当てられた後、qubit を操作や関数に渡すことができます。 *呼び出し* 可能とも呼ばれます。 これは、Q # プログラムが qubit を使用して実行できることです。Qubit の状態に対する直接的なアクションはすべて、やなどの *組み込み* 呼び出しが定義されてい [`X`](xref:Microsoft.Quantum.Intrinsic.X) ます。これは、その [`H`](xref:Microsoft.Quantum.Intrinsic.H) 実装が Q # で定義されておらず、ターゲットコンピューターによって定義されているものであるためです。 これらの操作は *、実際には、* 特定の q&a プログラムを実行するために使用するターゲットコンピューターによってのみ具体的に行われます。

たとえば、 [フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でプログラムを実行すると、シミュレーターはシミュレートされたクォンタムシステムに対応する数学的操作を実行します。
しかし、将来的に見てみると、ターゲットコンピューターが実際の quantum のコンピューターである場合、Q # でこのような操作を呼び出すと、*実際* のクォンタムシステムに対応する *実際* の操作を実行するように、クォンタムコンピューターが指示されます (正確に時間がかかるレーザーパルスなど)。

Q # プログラムは、ターゲットコンピューターによって定義されたこれらの操作を結合して、クォンタム計算を表す新しい高レベルの操作を作成します。
このように Q # を使用すると、対象のマシンまたはシミュレーターの構造に関しても一般的に、基になるクォンタムやハイブリッドクォンタム–クラシックアルゴリズムを簡単に表現できます。

単純な例として、$ \ket $ 状態に1つの qubit を割り当てて {0} から、Hadamard 操作を適用 `H` して結果を基に測定する次のプログラムがあり `PauliZ` ます。

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
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

Quantum [Katas](https://github.com/microsoft/QuantumKatas#introduction) は、一般的なクォンタム操作や qubits の操作方法など、 [クォンタムコンピューティングの概念](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) についての優れた概要を提供します。 その他の例につい [ては、「組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude)」も参照してください。



