---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716200"
---
# <a name="embedpauli-function"></a>EmbedPauli 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


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

