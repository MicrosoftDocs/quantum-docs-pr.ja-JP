---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853481"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


2つの操作を指定すると、すべての入力状態で同じ動作をするようにアサートされます。

このアサーションは、フォームのすべての状態に対して操作のアクションを確認することによって実装されます。 $V 0/otimes V_ {n-1} $ です。 $V _k $ は、状態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $、$ \ket{i} $ (+ 1 eigenstate of Pauli Y 演算子) です

このアサーションは $n $ qubits を使用し、比較対象の操作の複数の呼び出しを必要とします。

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

操作と演算を実行する qubits $n $ の数 `givenU` `expectedU` 。


### <a name="givenu--qubit--unit"></a>与え u: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits の操作を確認します。


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

比較対象の $n $ qubits に対する参照操作 `givenU` です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>References

州 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $、$ \ket{i} $ の基礎は、「 [ *i. 語,*](https://arxiv.org/abs/quant-ph/9610001)」で説明されているように、Chuang-Nielsen の基礎です。

## <a name="see-also"></a>参照

- [AssertOperationsEqualReferenced です。](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)