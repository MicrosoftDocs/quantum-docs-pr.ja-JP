---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846243"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


マップされたフォールドを1つの関数に結合します

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>説明

この関数は、 `fn` 初期状態から開始 `state` し、初期状態を含まないすべての中間値を返す、配列を通じて関数を反復処理します。

## <a name="input"></a>入力

### <a name="fn--statet---state"></a>fn: (' State, t)-> ' 状態

配列に対して折りたたむ関数


### <a name="state--state"></a>状態: ' 状態

折りたたむ初期状態


### <a name="array--t"></a>配列: ' t []

折りたたむ値の配列



## <a name="output--state"></a>出力: ' State []

最終状態を含むすべての中間状態。初期状態は含まれません。
出力配列の長さは、と同じ長さです `array` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="state"></a>' 状態

関数が操作する状態の種類 `fn` (つまり、最初の入力としてを受け取り、を返す)。
### <a name="t"></a>&

要素の型 `array` 。

## <a name="example"></a>例

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```