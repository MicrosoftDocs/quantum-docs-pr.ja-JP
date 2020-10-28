---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712187"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


Steane コードエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="data--qubit"></a>データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

入力 qubit である1つの qubit を保持する配列。


### <a name="scratch--qubit"></a>スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

冗長性を追加する6つの qubits を保持する配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

