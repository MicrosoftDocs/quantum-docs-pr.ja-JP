---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856805"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROMQubitCount は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> を使用してください。

によって返された操作に割り当てる必要がある qubits の合計数を返し `QuantumROM` ます。

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>入力

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットエラー $ \ イプシロン $。


### <a name="ncoeffs--int"></a>nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)

で指定された係数の数 `QuantumROM` 。



## <a name="output--intintint"></a>出力: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>最初のパラメーター

は、 `(x,(y,z))` `x = y + z` 割り当てられた qubits の合計数、は `y` レジスタの qubits の数、は `LittleEndian` `z` ガベージ qubits の数であるタプルです。