---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198947"
---
# <a name="i-operation"></a>I 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


1つの qubit で id 操作 (no op) を実行します。

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

これは、何の操作も行いません。 これは完全性を実現するために用意されています。また、アルゴリズムで id を呼び出したり、パラメーターとして渡したりすると便利な場合があります。