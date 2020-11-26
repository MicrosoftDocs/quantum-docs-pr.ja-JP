---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210115"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


古典的な整数と、qubits のレジスタによって表される整数の間のビットごとの XOR 演算を適用します。

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

`X`整数内の1ビットに基づいて、リトルエンディアンレジスタの qubits に操作を適用します。

`value`A と y は、でエンコードされた符号なし整数であることを示し `target` 、$ `InPlaceXorLE` \ket{y}\rightarrow \ket{y\oplus a} $ というマップによって指定された操作を実行します。 $-oplus $ はビットごとの排他的 or 演算子です。

## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

負でないと見なされる整数。


### <a name="target--littleendian"></a>ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`value`リトルエンディアンエンコーディングで格納するために使用されるクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

