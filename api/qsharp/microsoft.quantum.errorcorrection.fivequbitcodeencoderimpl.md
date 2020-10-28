---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712336"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>FiveQubitCodeEncoderImpl 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


5 qubit エンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="data--qubit"></a>データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

入力 qubit である1つの qubit を保持する配列。


### <a name="scratch--qubit"></a>スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

冗長性を追加する4つの qubits を保持する配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

選択された特定のエンコーダーは、ペーパー V. KliuchMaslov 氏と d. "Phys. Phys. 88, 052307 (2013); から取得されましたが、これは、「Clifford 回線の最適化」です。 https://arxiv.org/abs/1305.0810、図 4b) では、合計11ゲートが必要です。