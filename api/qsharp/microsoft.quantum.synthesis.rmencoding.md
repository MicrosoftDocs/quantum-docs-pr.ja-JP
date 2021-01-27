---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855340"
---
# <a name="rmencoding-function"></a>RMEncoding 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1} ブール値の真偽値のコーディング

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>入力

### <a name="b--bool"></a>b: [Bool](xref:microsoft.quantum.lang-ref.bool)

ブール値



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

が false の場合は1。それ以外の場合は `b` -1。