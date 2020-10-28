---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719107"
---
# <a name="ispermutation-function"></a>IsPermutation 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


指定された配列が順列を表す場合にのみ、true を出力します。

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>説明

長さの配列を指定した場合は `array` `n` 、の各整数がに `0` `n - 1` 1 回だけ出現し `array` 、 `array` 要素の順列として解釈できる場合にのみ、true を返し `n` ます。

## <a name="input"></a>入力

### <a name="permuation--int"></a>permuation: [Int](xref:microsoft.quantum.lang-ref.int)[]

順列を表すか、または表現できない配列。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>解説

長さゼロの配列は、普通の順列です。