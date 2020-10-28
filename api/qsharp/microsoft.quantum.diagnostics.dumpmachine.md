---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712873"
---
# <a name="dumpmachine-function"></a>DumpMachine 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


現在のターゲットコンピューターの状態をダンプします。

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>入力

### <a name="location--t"></a>場所: \

コンピューターのダンプを生成する場所に関する情報を提供します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

[なし] :

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

このメソッドを使用すると、ターゲットコンピューターの現在の状態に関する情報をファイルまたはその他の場所にダンプできます。
生成される実際の情報とのセマンティクス `location` は、各ターゲットコンピューターに固有です。 ただし、空のタプルを場所として指定 `()` する () か、パラメーターを省略するだけで、 `location` 通常はコンソールに出力を生成します。

Quantum 開発キットの一部として配布されたローカルの完全な状態シミュレーターでは、このメソッドは、wave 関数を1次元の複素数の配列として書き込むファイルのパスを含む文字列を想定しています。各要素は、対応する状態を測定する確率の振幅を表します。