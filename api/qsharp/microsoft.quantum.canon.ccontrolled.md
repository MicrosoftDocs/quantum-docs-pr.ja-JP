---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716592"
---
# <a name="ccontrolled-function"></a>CControlled 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


操作 op が指定された場合、は、従来の制御ビットが true の場合に op を適用する新しい操作を返します。 `false`の場合、何も起こりません。

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>入力

### <a name="op--t--unit"></a>op: t => [単位](xref:microsoft.quantum.lang-ref.unit) 

条件付きで適用する操作。



## <a name="output--boolt--unit"></a>出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

新しい操作。これは、クラシック制御ビットが true の場合の op です。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft......................](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft............](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft......................](xref:Microsoft.Quantum.Canon.CControlledCA)