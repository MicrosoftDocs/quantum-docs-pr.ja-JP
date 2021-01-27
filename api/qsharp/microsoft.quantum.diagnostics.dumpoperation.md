---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829278"
---
# <a name="dumpoperation-operation"></a>DumpOperation 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


操作が指定された場合、現在の実行ターゲットで使用できるようになった操作に関する診断が表示されます。

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

指定された操作が動作する qubits の数。


### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

診断される操作。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

クォンタムシミュレーターのターゲットで実行すると、次のスニペットはマトリックス $ $ \begin{aligned} を出力します (\begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>解説

この操作を呼び出すと、Q # 内からは観察可能な効果がありません。 表示されている正確な診断は、現在の実行ターゲットおよびエディター環境に依存しています。
たとえば、完全な状態のクォンタムシミュレーターで使用する場合は、を表すために使用される、1つの単位の行列 `op` が表示されます。

グローバルフェーズのあいまいさ (例: 完全な状態シミュレーター) を許可するシミュレーターで実行する場合、返される表現はグローバルフェーズによって異なる場合があることに注意してください。

同様に、行と列の行列表現の順序は、この操作をサポートする各シミュレーターで使用される規則によって異なる場合があります。