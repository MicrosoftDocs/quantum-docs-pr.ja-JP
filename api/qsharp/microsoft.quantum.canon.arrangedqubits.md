---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: 並べ替え Edqubits 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217069"
---
# <a name="arrangedqubits-function"></a>並べ替え Edqubits 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


インデックスに基づいてコントロール、ターゲット、ヘルパーの qubits を整列する

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>説明

インデックス0のターゲットを持つ Qubit 配列を返し、インデックス 2 ^ i のコントロール i を返します。  ヘルパーの qubits は、配列内の他のすべての位置に挿入されます。

## <a name="input"></a>入力

### <a name="controls--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>ヘルパー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

