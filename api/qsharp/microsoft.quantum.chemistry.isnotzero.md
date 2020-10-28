---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714828"
---
# <a name="isnotzero-function"></a>IsNotZero 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パック [](https://nuget.org/packages/)


`Double`数値が約0以外であるかどうかを確認します。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>入力

### <a name="number--double"></a>数値: [Double](xref:microsoft.quantum.lang-ref.double)

確認する数値



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`number`の値がを超える絶対値を持つ場合に true を返し `1e-15` ます。