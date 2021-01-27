---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833835"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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