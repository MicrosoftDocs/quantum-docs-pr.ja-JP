---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827796"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


現在使用できる qubits の数を返します。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

ステートメントで割り当てることができる qubits の数 `using` 。
使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。

## <a name="see-also"></a>参照

- [GetQubitsAvailableToBorrow (Microsoft Quantum)](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)