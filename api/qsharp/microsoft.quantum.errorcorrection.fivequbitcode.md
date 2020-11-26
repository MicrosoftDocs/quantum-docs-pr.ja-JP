---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Fivvldb Bitcode 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200885"
---
# <a name="fivequbitcode-function"></a>Fivvldb Bitcode 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦5、1、3⟧のコードエンコーダーを表す QECC 値と、インプレースより隣人測定値を返します。

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)

型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。

## <a name="remarks"></a>解説

このコードは、次の2つのホワイトペーパーで個別に検出されました。

- C. H. Bennett、d. DiVincenzo、j.。 Smolin と W. K。 Wootters、"Mixed state 結び付き and クォンタム error 修正、" Phys, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 および
- R. Laflamme、C. Miquel、J. P。 ラパスと W. H. Zurek、"完全なクォンタムエラー修正コード" Phys. Lett. 77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019