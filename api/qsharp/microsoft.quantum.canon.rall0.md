---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715631"
---
# <a name="rall0-operation"></a>RAll0 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


フェーズシフト操作を実行します。

$R = \ bold one-(1-e ^ {i \phi}) \ket{0\cdots 0} \bra{0\cdots 0} $。

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="phase--double"></a>フェーズ: [Double](xref:microsoft.quantum.lang-ref.double)

フェーズ $ \ phi $ は、状態 $ \ket{0\cdots 0} \bra{0\cdots 0} $ に適用されています。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

$R $ によって回転される状態を持つレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft. RAll1](xref:Microsoft.Quantum.Canon.RAll1)