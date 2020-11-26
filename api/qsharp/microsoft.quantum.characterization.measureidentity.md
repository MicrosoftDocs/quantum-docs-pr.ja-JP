---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216117"
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