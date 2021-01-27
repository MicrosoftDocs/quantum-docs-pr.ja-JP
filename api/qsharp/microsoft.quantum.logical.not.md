---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849089"
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

```qsharp
let x = not value;
let x = Not(value);
```