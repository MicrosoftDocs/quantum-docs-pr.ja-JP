---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 0a5a028f85b80575b754b93a797a1460d21bb552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853188"
---
# <a name="bitflipcode-function"></a>BitFlipCode 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦3、1、1⟧ビットフリップコードエンコーダー、および埋め込み先より隣人測定値を持つデコーダーを表す QECC 値を返します。

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)

型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。