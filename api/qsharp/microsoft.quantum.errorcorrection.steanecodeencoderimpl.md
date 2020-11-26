---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 3a9a1b11ed9255f18135e3717de7e9e1ec891298
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200427"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Steane コードエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="data--qubit"></a>データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

入力 qubit である1つの qubit を保持する配列。


### <a name="scratch--qubit"></a>スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

冗長性を追加する6つの qubits を保持する配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

