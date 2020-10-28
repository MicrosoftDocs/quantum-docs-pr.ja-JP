---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721363"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


クォンタムレジスタの特定の状態の確率に予期される値があることをアサートします。

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>説明

$ \Ket{\psi} = \ sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ という $n が指定されている場合、$j $ によってインデックスが作成された状態 $ \ket{j} $ の確率 $ | \ alpha_j | ^ 2 $ が予期される値であることをアサートします。

## <a name="input"></a>入力

### <a name="stateindex--int"></a>stateIndex: [Int](xref:microsoft.quantum.lang-ref.int)

レジスタによって表される状態 $ \ket{j} $ の $j $ のインデックス `LittleEndian` 。


### <a name="expected--double"></a>が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)

予期される値 $ | \ alpha_j | ^ 2 $。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

リトルエンディアン形式で $ \ket{\psi} $ を格納する qubit レジスタ。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

実際と予想される差に対する絶対許容値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

