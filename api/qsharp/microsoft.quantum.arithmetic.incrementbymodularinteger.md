---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222951"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


整数定数によって、qubit レジスタのモジュール単位インクリメントを実行します。

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

$ `increment` `modulus` と `target` $y $ によってエンコードされた整数を $N $a $ を意味します。
その後、次の変換が実行されます。 \begin{align} \ket{y} \ mapare \ket{(y + a) \ 演算子名 {mod} N} \end{align} 整数はリトルエンディアン形式でエンコードされます。

## <a name="input"></a>入力

### <a name="increment--int"></a>increment: [Int](xref:microsoft.quantum.lang-ref.int)

$Y $ に加算する $ $a 整数値。


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

Mods $y + a $ の整数 $N $。


### <a name="target--littleendian"></a>ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`LittleEndian` `increment` $A $ が追加される形式の整数 $y $。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

Target の初期値が $N $ より小さく、$ $a $ が $N $ より小さいことを前提としています。
は <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 、ベースで同じ操作を実装することに注意して `PhaseLittleEndian` ください。

## <a name="see-also"></a>参照

- [IncrementPhaseByModularInteger です。](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)