---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223546"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


上の ApplyOuterCDKMAdder 操作と共に使用される RippleCarryAdderCDKM のコア操作。つまり、この操作で RippleCarryAdderCDKM の内部操作を取得します。 この操作では、繰越 qubit を計算し、入力の一部ではないゲートのシーケンスを適用し `ys` ます。

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

最初の qubit レジスタ。


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

2番目の qubit レジスタ。


### <a name="ancilla--qubit"></a>ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

この操作に渡された RippleCarryAdderCDKM で使用される ancilla qubit。


### <a name="carry--qubit"></a>キャリー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

RippleCarryAdderCDKM 操作で qubit を実行します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>リファレンス

- Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。
  https://arxiv.org/abs/quant-ph/0410184v1