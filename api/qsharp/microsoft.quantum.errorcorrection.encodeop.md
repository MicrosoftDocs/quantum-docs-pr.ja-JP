---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712350"
---
# <a name="encodeop-user-defined-type"></a>EncodeOp ユーザー定義型

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パック [](https://nuget.org/packages/)


指定されたスクラッチを使用して、物理レジスタを論理レジスタにエンコードする操作を表します。

最初の引数はエンコードされる物理レジスタとして取得され、2番目の引数は使用されるスクラッチレジスタとして使用されます。

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

