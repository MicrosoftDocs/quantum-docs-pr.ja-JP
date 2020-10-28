---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725575"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


ブロックエンコードのリフレクションをクォンタムウォークに変換します。

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>説明

$W `BlockEncodingReflection` 対象の $H 演算子をエンコードする $U $ で表されるが指定されている場合は、$-pm e ^ {\ pm i\ sin ^ {-1} (H)} $ の範囲を含むクォンタムウォーク $ に変換します。

## <a name="input"></a>入力

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`クォンタムウォークに変換するための、$U の ' $ ' を指定します。



## <a name="output--qubitqubit--unit-adj--ctl"></a>出力: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl

クォンタムウォーク $W $ はレジスタに対して共同で動作し、$ `a` `s` $H-pm e ^ {\ pm i\ sin ^ {-1} (H)} $ の範囲を含んでいます。

## <a name="references"></a>関連項目

- Hamiltonian シミュレーション Qubitization Guang Hao Low、Isaac L. 語 https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>参照

- [Microsoft. クォンタム. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection です。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)