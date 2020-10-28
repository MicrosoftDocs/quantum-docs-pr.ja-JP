---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713064"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


この操作とその adjoint の呼び出しの間に、指定された操作が特定の回数だけ呼び出されることをアサートします。

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>入力

### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

を `op` 呼び出すことができる最大回数。


### <a name="op--tinput--toutput-adj--ctl"></a>op: ' TInput => ' TOutput 形容詞 + Ctl

呼び出しが制限される操作。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

失敗したときに表示されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="remarks"></a>解説

この操作は、サポートされていない非 op ターゲットに置き換えることができます。