---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195377"
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