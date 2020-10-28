---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711678"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

名前空間: [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing) .. 拡張子

パック [](https://nuget.org/packages/)


> [!WARNING]
> AssertOperationsEqualInPlace は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> を使用してください。
>
> @"microsoft.quantum.diagnostics.assertoperationsequalinplace" を使用してください。
> この操作の引数の順序が変更されていることに注意してください。



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>入力

### <a name="actual--qubit--unit"></a>実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 




### <a name="expected--qubit--unit-adj"></a>想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞




### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

