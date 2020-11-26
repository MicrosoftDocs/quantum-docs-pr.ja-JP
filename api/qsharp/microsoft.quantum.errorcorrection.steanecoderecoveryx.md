---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200372"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦7、1、3⟧ Steane 量子コードの安定板グループの X 部分のデコーダー。

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>入力

### <a name="syndrome--syndrome"></a>より隣人: [より隣人](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

安定板の X 部を測定して取得したより隣人配列。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

エンコードされたクォンタムシステムに適用されるときに、に対応するエラーを修正する、Pan Li 操作の配列 `syndrome` 。

## <a name="remarks"></a>解説

選択したデコーダーは、⟦7、1、3⟧ Steane code の CSS コードプロパティを使用します。つまり、X エラーと Z エラーを個別に修正します。 コードのプロパティとして、X の位置 (それぞれ、適用される Z 補正) は X の3ビットエンコーディング、それぞれ Z より隣人は整数であると見なされます。

## <a name="references"></a>リファレンス

- D. Gottesman、"安定板のコードとクォンタムのエラーの修正" 博士、Thesis、Caltech、1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>参照

- [SteaneCodeRecoveryX を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [SteaneCodeRecoveryFns を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)