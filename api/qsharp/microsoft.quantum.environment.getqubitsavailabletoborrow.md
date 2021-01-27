---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853244"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


現在借用で使用可能な qubits の数を返します。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

借用可能で、ステートメントの一部として割り当てられない qubits の数 `borrowing` 。
使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。

## <a name="see-also"></a>参照

- [GetQubitsAvailableToUse (Microsoft Quantum)](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)