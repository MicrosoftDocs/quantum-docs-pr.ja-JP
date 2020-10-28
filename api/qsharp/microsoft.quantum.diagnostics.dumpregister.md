---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712840"
---
# <a name="dumpregister-function"></a>DumpRegister 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


指定した qubits に関連付けられている現在のターゲットコンピューターの状態をダンプします。

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="location--t"></a>場所: \

状態のダンプを生成する場所に関する情報を提供します。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

報告する qubits の一覧。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

[なし] :

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

このメソッドを使用すると、指定した qubits の状態に関連付けられた情報をファイルまたはその他の場所にダンプできます。
生成される実際の情報とのセマンティクス `location` は、各ターゲットコンピューターに固有です。 ただし、空のタプルを位置 () として指定 `()` することは、通常、出力をコンソールに生成することを意味します。

Quantum 開発キットの一部として配布されるローカルの完全な状態シミュレーターでは、このメソッドは、指定された qubits の状態 (つまり、対応するサブシステムの wave 関数) を1次元の複素数の配列として書き込むファイルのパスを持つ文字列を受け取ります。各要素は、対応する状態を測定する確率の振幅を表します
指定した qubits が他の qubits と区別され、その状態を分離できない場合は、qubits がありであることを報告するだけです。