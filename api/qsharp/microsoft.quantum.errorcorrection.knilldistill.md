---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853114"
---
# <a name="knilldistill-operation"></a>KnillDistill 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Knill マジック state 取り組みアルゴリズムを実装します。

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>説明

マジックステート $ $ \begin{align} \cos\frac{\pi} \ket + \ sin \frac{\pi} \ket \end{align} の15の概数コピーを指定すると {8} {0} {8} {1} 、$ $ により高品質のコピーが1つ生成されます。

## <a name="input"></a>入力

### <a name="roughmagic--qubit"></a>roughMagic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

マジック状態の概数コピーを含む 15 qubits のレジスタ。 この取り組みプロシージャを適用する `roughMagic[0]` と、1つの高品質のコピーが含まれ、レジスタの残りの部分は $ \ket{00\cdots 0} $ 状態にリセットされます。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

の場合、 `true` プロシージャは成功し、高品質のコピーが受け入れられます。 の場合、 `false` プロシージャは失敗し、レジスタの状態は未定義であると見なされます。

## <a name="remarks"></a>解説

Knill のアルゴリズムに従います。
ただし、現在の実装は、使用される qubits が多すぎるため、最適な実装ではありません。
このルーチンでは、マジック状態が挿入されます。この場合、より優れたプロトコルが使用されます。

## <a name="references"></a>References

- [Knill](https://arxiv.org/abs/quant-ph/0402171)