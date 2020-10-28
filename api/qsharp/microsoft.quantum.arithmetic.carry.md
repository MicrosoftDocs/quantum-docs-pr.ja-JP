---
uid: Microsoft.Quantum.Arithmetic.Carry
title: キャリー操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721310"
---
# <a name="carry-operation"></a>キャリー操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


元に戻す伝達ゲートを実装します。 Qubit でエンコードされたキャリービット `carryIn` と、およびでエンコードされた2つの summand ビットがある `summand1` `summand2` 場合、はのビットごとの xor を計算し、 `carryIn` `summand1` `summand2` qubit で `summand2` は xor は qubit に対してになり `carryOut` ます。

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="carryin--qubit"></a>carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

実行中の qubit。


### <a name="summand1--qubit"></a>summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初の summand qubit。


### <a name="summand2--qubit"></a>summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

2番目の summand qubit は、との合計の下位ビットに置き換えられ `summand1` `summand2` ます。


### <a name="carryout--qubit"></a>carryOut: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

繰越 qubit は、合計のビットの xor になります。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

