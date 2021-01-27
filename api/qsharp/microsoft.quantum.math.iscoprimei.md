---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851365"
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