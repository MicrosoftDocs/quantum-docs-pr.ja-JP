---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709863"
---
# <a name="not-function"></a>Not 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


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