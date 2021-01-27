---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839593"
---
# <a name="isnotzero-function"></a>IsNotZero 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


`Double`数値が約0以外であるかどうかを確認します。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>入力

### <a name="number--double"></a>数値: [Double](xref:microsoft.quantum.lang-ref.double)

確認する数値



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`number`の値がを超える絶対値を持つ場合に true を返し `1e-15` ます。