---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712518"
---
# <a name="applybitflipencoder-operation"></a>ApplyBitFlipEncoder 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


ビットフリップエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。

このエンコーダーは、インプレース整合性復旧を利用できることに注意してください。この場合、の初期状態で記述されたエラーが "発生" し `auxQubits` ます。
特に、 `auxQubits` が最初に状態が $ \ket $ の場合、これにより、エンコードされ {10} た qubit で $X _1 $ error が発生します。

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="coherentrecovery--bool"></a>coherentRecovery: [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

- doi: 10.1103/PhysRevA