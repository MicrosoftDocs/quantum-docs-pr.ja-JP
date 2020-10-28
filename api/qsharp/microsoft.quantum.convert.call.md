---
uid: Microsoft.Quantum.Convert.Call
title: 操作の呼び出し
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713531"
---
# <a name="call-operation"></a>操作の呼び出し

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


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