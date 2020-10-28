---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721214"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


符号なし整数を表す qubit レジスタの最上位ビットを `from` qubit にコピーし `target` ます。

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="from--littleendian"></a>from: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

最上位ビットのコピー元の符号なし整数。
整数は、リトルエンディアン形式でエンコードされます。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最上位ビットがコピーされる qubit。 ビットエンコードは計算に基づいています。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [LittleEndian です。](xref:Microsoft.Quantum.Arithmetic.LittleEndian)