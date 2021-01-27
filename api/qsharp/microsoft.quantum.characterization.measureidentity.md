---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851824"
---
# <a name="measureidentity-operation"></a>MeasureIdentity 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits のレジスタで id 演算子を測定します。

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>入力

### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

測定するレジスタ。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

結果の値 `Zero` 。

## <a name="remarks"></a>解説

$/を完了した $ は eigenvalue $1 $ のみを持ち、負の eigenvalue を持たないため、この操作は常にを返し `Zero` ます。これは eigenvalue $ + 1 = (-1) ^ 0 $ に相当します。の状態を折りたたむことはできません `register` 。

実際には、この操作は役に立ちませんが、プロセス tomography のコンテキストでは、クォンタムプロセスのトレース保持に関する情報を提供するので役立ちます。
特に、損失の多い測定値を持つターゲットコンピューターでは、この操作を実際の測定値 $/bold で置き換える必要があります。