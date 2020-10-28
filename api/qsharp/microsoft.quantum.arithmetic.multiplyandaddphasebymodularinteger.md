---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719803"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


MultiplyAndAddByModularInteger と同じですが、summand が QFT ベースで整数をエンコードすることを前提としています。

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>入力

### <a name="constmultiplier--int"></a>[型の型: Int](xref:microsoft.quantum.lang-ref.int)

各 basis 状態ラベルに追加する整数 $a $。


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

に関して、加算と乗算が行われる剰余 $N $。


### <a name="multiplier--littleendian"></a>乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

は `phaseSummand` 、の最上位ビットが0に設定されていることを前提としています。
また、の値が $N $ 未満であることを前提としてい `phaseSummand` ます。

## <a name="see-also"></a>参照

- [MultiplyAndAddByModularInteger です。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)