---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202942"
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