---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712957"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


2つの操作を指定すると、すべての入力状態で同じ動作をするようにアサートされます。

このアサーションは、Jamiołkowski isomorphism を使用することによって実装されます。このアサーションは、2つのありレジスタの qubit 状態アサーションのいずれかに軽減されます。
このため、この操作では、テスト対象の各操作を1回だけ呼び出す必要がありますが、割り当てられる qubits は2倍必要です。
このアサーションを使用して、最適化されたバージョンの操作がその単純な実装と同じように動作すること、またはクォンタム以外の入力の範囲に対して動作する操作が既知のケースと一致することを確認できます。

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

各操作に渡す qubits の数。


### <a name="actual--qubit--unit"></a>実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

テストする操作。


### <a name="expected--qubit--unit-adj"></a>想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

テスト対象の操作の予期される動作を定義する操作。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作を行うには、予期される動作をモデル化する操作が adjointable であることが必要です。これにより、逆のをターゲットレジスタだけで実行できるようになります。
正式には、この要件を緩和されする置換操作を指定できますが、入れ替え操作は、通常、任意のクォンタム操作に対して物理的には機能しないため、ここにはオプションとして含まれていません。