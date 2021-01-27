---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840533"
---
# <a name="embedpauli-function"></a>EmbedPauli 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Single qubit の P# li 演算子と qubit のインデックスが指定されている場合、そのインデックスの指定された単一の qubit 演算子と `PauliI` 他のすべてのインデックスで、マルチ qubit の P# li 演算子を返します。

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li

指定された場所に配置される単一の qubit の P# li 演算子。


### <a name="location--int"></a>場所: [Int](xref:microsoft.quantum.lang-ref.int)

インデックス。ここで `output[location] == pauli` 、 `output` はこの関数の出力です。


### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

返される配列の長さ。



## <a name="output--pauli"></a>出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="example"></a>例

配列を取得するには、次のようにし `[PauliI, PauliI, PauliX, PauliI]` ます。

```qsharp
EmbedPauli(PauliX, 2, 3);
```