---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200477"
---
# <a name="steanecode-function"></a>SteaneCode 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦7、1、3⟧ Steane code encoder およびデコーダーを、インプレースより隣人測定値と共に表す CSS 値を返します。

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>出力: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

⟦7、1、3⟧ Steane code のエンコーディングとエラー修正を実行するために、関連するすべてのデータを収集する CSS 型のオブジェクト。

## <a name="remarks"></a>解説

このコードは、次のホワイトペーパーに記載されています。

- A. Steane、「複数のパーティクル干渉と量子エラー修正」、Proc。 Roy. Lond。 A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.