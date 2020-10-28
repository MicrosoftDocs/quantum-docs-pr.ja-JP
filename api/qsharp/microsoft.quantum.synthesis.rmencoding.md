---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725477"
---
# <a name="rmencoding-function"></a>RMEncoding 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


{-1,1} ブール値の真偽値のコーディング

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>入力

### <a name="b--bool"></a>b: [Bool](xref:microsoft.quantum.lang-ref.bool)

ブール値



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

が false の場合は1。それ以外の場合は `b` -1。