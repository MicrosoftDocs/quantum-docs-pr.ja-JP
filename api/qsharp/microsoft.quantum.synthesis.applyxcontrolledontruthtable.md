---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725248"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


の @"microsoft.quantum.intrinsic.x" `target` クラシック代入に対してブール関数が true と評価された場合に、操作をに適用し `func` `controlRegister` ます。

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>説明

この操作は、\begin{align} U\ket {x} \ k {y} = \ket{x}\ket{y/oplus f (x)} \end{align} を実装します。ここで $x $ と $y $ `controlRegister` `target` はそれぞれとを表します。

ブール関数 $f $ は、大規模な整数の観点から真理値テーブルとして表されます。
たとえば、3つの入力に対するマジョリティ関数は bitstring によって表されます。この場合、 `11101000` 最上位ビットは `1` 入力割り当てに相当し、最下位 `(1, 1, 1)` ビットは `0` 入力割り当てに相当し `(0, 0, 0)` ます。
これは、 `0xE8L` 16 進数表記では、または10進表記のように、大きい整数で表すことができ `232L` ます。  サフィックスは、 `L` 定数が型であることを示し `BigInt` ます。
この表現の詳細については、 [真理テーブル kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)も参照してください。

実装では @"microsoft.quantum.intrinsic.cnot" 、およびゲートを使用し @"microsoft.quantum.intrinsic.r1" ます。

## <a name="input"></a>入力

### <a name="func--bigint"></a>func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ブール型の真理値テーブルを大きな整数として表現


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

制御 qubits の登録


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット qubit



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

- [*Schuch* 、 *Siewert* 、prl 91、no. 027902、2003、arxiv: quant-ph/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* , *Martin Roetteler* , arxiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>参照

- [ApplyXControlledOnTruthTableWithCleanTarget です。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)