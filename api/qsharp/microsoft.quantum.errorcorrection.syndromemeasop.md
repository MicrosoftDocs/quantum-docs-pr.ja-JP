---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Syn% Memeasop ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850052"
---
# <a name="syndromemeasop-user-defined-type"></a>Syn% Memeasop ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


エラー修正コードブロックのより隣人を測定するために使用される操作を表します。

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a>例

ビットフリップコード $S = \ langle ZZI、IZZ \rangle $ のメジャー syndromes を、非フォールトトレラントな方法でスクラッチ qubits を使用して測定します。

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a>解説

このシグネチャは、 `(LogicalRegister => Syndrome)` の qubits と、補助 qubits `LogicalRegister` の後に補助 qubits の測定値を指定して、 `Syndrome` これらの測定値を表す値を抽出する操作を表し `Result[]` ます。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [より隣人を修正します。](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)