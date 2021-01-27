---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852323"
---
# <a name="permutequbits-operation"></a>PermuteQubits 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


スワップ操作を使用した Permutes qubits。

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="ordering--int"></a>順序付け: [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubits の新しい順序について説明します。ここで、インデックス i の qubits は [i] の順に並べられます。


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

順序 = [2, 1, 0] と register $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $、PermuteQubits によってレジスタが $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $ に変更されます

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```