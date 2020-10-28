---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712588"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)

パック [](https://nuget.org/packages/)


現在借用で使用可能な qubits の数を返します。
これには未使用の qubits が含まれます。つまり、これにはによって返される qubits が含まれ `GetQubitsAvailableToUse` ます。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

ステートメントで割り当てることができる qubits の数 `borrowing` 。
使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。

## <a name="see-also"></a>参照

- [GetQubitsAvailableToUse (Microsoft Quantum)](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)