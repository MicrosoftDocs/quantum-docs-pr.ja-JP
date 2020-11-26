---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Id の処理操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210439"
---
# <a name="prepareidentity-operation"></a>Id の処理操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタが指定されている場合、そのレジスタを下回っ混合状態で準備します。

レジスタは、depolarizing チャネル全体を各 qubit に適用することで、$/bold done/2 ^ N $ 状態で準備されます。ここで $N $ はレジスタの長さです。

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

前に説明した方法で状態を depolarized するレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [PrepareSingleQubitIdentity の準備](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)