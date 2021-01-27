---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843400"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>例

このレジスタでは、 `qubits` 3-qubit クォンタムの状態 $ \ket{\psi} = \ sqrt {1/8} \ k {0} + \ sqrt {7/8} \ k {6} $ をリトルエンディアン形式でエンコードするとします。
これは、番号が $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ と $ \ket \equiv\ket \ket \ket $ {6} {0} {1} {1} であることを意味します。 その後、次のアサートは成功します。

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```