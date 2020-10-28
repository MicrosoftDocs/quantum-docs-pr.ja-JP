---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713512"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


関数を操作に変換します。

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>説明

関数を指定した場合、その関数を呼び出す操作を返します。それ以外は何も行いません。

## <a name="input"></a>入力

### <a name="fn--input---output"></a>fn: ' Input-> ' 出力

操作に変換される関数。



## <a name="output--input--output"></a>出力: ' Input => ' 出力 

`op` `op(input)` すべてのと同一の操作 `fn(input)` `input` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="input"></a>' 入力

変換する関数の入力型。
### <a name="output"></a>' 出力

変換する関数の出力の種類。

## <a name="remarks"></a>解説

これは主に、操作を入力として受け取る関数または操作に関数を渡す場合に便利です。