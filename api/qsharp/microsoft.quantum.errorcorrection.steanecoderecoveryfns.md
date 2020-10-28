---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712140"
---
# <a name="steanecoderecoveryfns-function"></a>SteaneCodeRecoveryFns 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


⟦7、1、3⟧ Steane 量子コードの安定板グループの X 部と Z 部を組み合わせたデコーダーです。

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>出力: ([recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)、[recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))

`RecoveryFn`より隣人の測定値を受け取り、 `Result[]` `Pauli[]` 検出されたエラーを修正する操作を返す、型の関数のタプル。

## <a name="see-also"></a>参照

- [SteaneCodeRecoveryX を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [SteaneCodeRecoveryZ を修正します。](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)