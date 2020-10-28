---
uid: Microsoft.Quantum.Arrays.Fold
title: フォールド関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719210"
---
# <a name="fold-function"></a>フォールド関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列を使用して関数を反復処理し `f` `array` 、を返し `f(f(f(initialState, array[0]), array[1]), ...)` ます。

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>入力

### <a name="folder--statet---state"></a>フォルダー: (' State, ' \)-> ' 状態

配列に対して折りたたむ関数。


### <a name="state--state"></a>状態: ' 状態

フォルダーの初期状態です。


### <a name="array--t"></a>配列: ' t []

折りたたむ値の配列。



## <a name="output--state"></a>出力: ' 状態

のすべての要素を反復処理した後に、フォルダーによって返される最終的な状態 `array` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="state"></a>' 状態

関数が操作する状態の型 `folder` 。つまり、最初の引数としてを受け取り、を返します。
### <a name="t"></a>&

要素の型 `array` 。