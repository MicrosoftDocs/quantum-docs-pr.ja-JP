---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716485"
---
# <a name="composedoutput-function"></a>ComposedOutput 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


`inner`指定された入力に対するとの構成の出力を返し `outer` ます。

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>入力

### <a name="outer--u---v"></a>外部: ' U-> ' V




### <a name="inner--t---u"></a>内部: > ' U




### <a name="target--t"></a>ターゲット: \





## <a name="output--v"></a>出力: ' V



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U


### <a name="v"></a>' V

