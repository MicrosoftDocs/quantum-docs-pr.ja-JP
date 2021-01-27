---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841012"
---
# <a name="ccontrolled-function"></a>CControlled 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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