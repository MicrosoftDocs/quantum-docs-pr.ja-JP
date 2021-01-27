---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 474146e644bcd042e85b917bc43135a674bedce1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846886"
---
# <a name="inversemodi-function"></a>InverseModI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


は $ $b を返します。この場合、$a \ cdot b = 1 (\texttt{modulus}) $ となります。

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

反転されている数値


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

数値の反転に使用される剰余



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

$ $B $ (&) $a \ cdot b = 1 (\ 演算子 name{mod} \texttt{modulus}) $