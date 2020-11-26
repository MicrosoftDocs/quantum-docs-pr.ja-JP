---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197451"
---
# <a name="not-function"></a>Not 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


値のブール型の否定を返します。

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>入力

### <a name="value--bool"></a>値: [Bool](xref:microsoft.quantum.lang-ref.bool)

符号を反転する値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``value`がの場合にのみ `false` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let x = not value;
let x = Not(value);
```