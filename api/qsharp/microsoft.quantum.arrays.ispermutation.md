---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848092"
---
# <a name="ispermutation-function"></a>IsPermutation 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>例

次の Q # コードは、"すべての診断が正常に完了しました" というメッセージを出力します。

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>解説

長さゼロの配列は、普通の順列です。