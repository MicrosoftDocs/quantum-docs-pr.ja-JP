---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720026"
---
# <a name="i-operation"></a>I 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


1つの qubit で id 操作 (no op) を実行します。

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

これは、何の操作も行いません。 これは完全性を実現するために用意されています。また、アルゴリズムで id を呼び出したり、パラメーターとして渡したりすると便利な場合があります。