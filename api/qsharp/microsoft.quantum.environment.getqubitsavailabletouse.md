---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712579"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)

パック [](https://nuget.org/packages/)


現在使用できる qubits の数を返します。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

ステートメントで割り当てることができる qubits の数 `using` 。
使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。

## <a name="see-also"></a>参照

- [GetQubitsAvailableToBorrow (Microsoft Quantum)](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)