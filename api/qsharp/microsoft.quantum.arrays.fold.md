---
uid: Microsoft.Quantum.Arrays.Fold
title: フォールド関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848603"
---
# <a name="fold-function"></a>フォールド関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>例

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```