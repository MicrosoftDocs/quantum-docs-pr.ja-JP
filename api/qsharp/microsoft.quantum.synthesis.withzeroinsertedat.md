---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withゼロの付いた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855207"
---
# <a name="withzeroinsertedat-function"></a>Withゼロの付いた関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


0ビットを整数に挿入する

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>説明

この操作では、整数を取得し、ビットを0に挿入して、 `position` 更新された値を整数として返します。  たとえば、数値 10 ($10 _ = 1010_ $) の位置2に0を挿入すると、 {10} {2} 数値 18 ($18 _ {10} = 10010_ {2} $) が返されます。

## <a name="input"></a>入力

### <a name="position--int"></a>position: [Int](xref:microsoft.quantum.lang-ref.int)

0が挿入される位置。


### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

変更される値



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

変更された値