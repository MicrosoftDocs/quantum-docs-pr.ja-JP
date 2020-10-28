---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712971"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


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


### <a name="expectedu--qubit--unit-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

比較対象の $n $ qubits に対する参照操作 `givenU` です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

州 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $、$ \ket{i} $ の基礎は、「 [ *i. 語,*](https://arxiv.org/abs/quant-ph/9610001)」で説明されているように、Chuang-Nielsen の基礎です。

## <a name="see-also"></a>参照

- [AssertOperationsEqualReferenced です。](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)