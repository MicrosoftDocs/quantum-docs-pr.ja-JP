---
uid: Microsoft.Quantum.Convert.Call
title: 操作の呼び出し
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214213"
---
# <a name="call-operation"></a>操作の呼び出し

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された入力を使用して関数を呼び出します。

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>説明

関数とその関数への入力を指定すると、は関数を呼び出し、その出力を返します。

## <a name="input"></a>入力

### <a name="fn--input---output"></a>fn: ' Input-> ' 出力

呼び出される関数。


### <a name="input--input"></a>入力: ' 入力

関数に渡される入力。



## <a name="output--output"></a>出力: ' 出力

`fn` の呼び出しの結果。

## <a name="type-parameters"></a>型パラメーター

### <a name="input"></a>' 入力


### <a name="output"></a>' 出力



## <a name="remarks"></a>解説

この操作は、主に、操作内の特定の場所で関数を呼び出す場合や、操作が必要な関数を呼び出す場合に便利です。