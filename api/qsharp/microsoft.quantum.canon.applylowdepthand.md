---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209317"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定されたターゲットの qubit が、両方のコントロール qubit が1状態 (T 深度 1) である場合にのみ、測定を使用して adjoint 操作を実行します。

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

`target`両方のコントロールが1で、 `target` が状態が0であると想定している場合にのみ、を反転させます。  この操作には、T カウント4、T 深度1があり、1つのヘルパー qubit が必要です。このため、が0であることがわかっている場合は、CCNOT 操作に適している可能性があり `target` ます。  この操作の adjoint は測定ベースであり、T ゲートを必要とせず、ヘルパー qubit も必要としません。

## <a name="input"></a>入力

### <a name="control1--qubit"></a>control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初のコントロールの qubit


### <a name="control2--qubit"></a>control2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

2番目のコントロール qubit


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット補助 qubit;状態は0である必要があります



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>リファレンス

- Cody Jones: 「fault トレラントな Toffoli ゲートのための斬新構造」、「Phys 87、022328、2013 [Arxiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA
- Peter Selinger: "T 深度 one のクォンタム回線"、Phys 87、042302、2013 [Arxiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA 87.042302