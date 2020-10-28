---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712420"
---
# <a name="decodefromsteanecode-operation"></a>DecodeFromSteaneCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


エンコードされていないクォンタムレジスタを⟦7、1、3⟧ Steane 量子コードでエンコードされたクォンタムレジスタにマップする逆エンコード操作。

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>入力

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

エンコードされた 5-qubits コードの論理状態を表す qubits の配列。



## <a name="output--qubitqubit"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

2番目のパラメーターの補助 qubit と共に、最初のパラメーターのエンコードされていない状態を表す、値1の qubit 配列。

## <a name="remarks"></a>解説

選択したデコーダーは、⟦7、1、3⟧ Steane code の CSS コードプロパティを使用します。つまり、X エラーと Z エラーを個別に修正します。 コードのプロパティとして、X の位置 (それぞれ、適用される Z 補正) は X の3ビットエンコーディング、それぞれ Z より隣人は整数であると見なされます。

## <a name="references"></a>関連項目

- D. Gottesman、"安定板のコードとクォンタムのエラーの修正" 博士、Thesis、Caltech、1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>参照

- [SteaneCodeEncoder を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [SteaneCodeDecoder を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)