---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712495"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


⟦ 3, 1, 1 ⟧ビットフリップコードのテーブル参照によって指定されたより隣人測定の復旧 p 操作のための関数です。

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>出力: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`より隣人の測定値を受け取り、 `Result[]` `Pauli[]` 検出されたエラーを修正する操作を返す型の関数。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)