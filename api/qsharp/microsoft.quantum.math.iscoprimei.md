---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195360"
---
# <a name="iscoprimei-function"></a>IsCoprimeI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


$A $ と $b $ が共存している場合は true、それ以外の場合は false を返します。

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

primality がテストされている最初の数


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

テストされている共同 primality の2番目の数



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

$A $ と $b $ が共存している場合 (たとえば、最も一般的な除数が 1) の場合は True、それ以外の場合は false です。