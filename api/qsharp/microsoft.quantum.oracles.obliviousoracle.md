---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710992"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パック [](https://nuget.org/packages/)


Oracle for 無関係の振幅増幅を表します。

Oracle $O $ への入力は次のとおりです。

- $ Act $O ancilla register $a $。
- システム登録 $s $ は、必要な $U $ が適用され、レジスタ $a $ が状態 $ \ket{t} a $ にあることを示しています \_ 。

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>解説

この oracle で定義されている $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket{t ^ \ perp} \_ a\ cドット $ $ \_ \ket{t} a $ でフラグが設定されたベースで、任意のシステム状態 $ \ket{\psi} s $ に対して、ancilla state $ \ket{s} a $ を使用して、任意のシステム状態 $ s \_ $ に対し \_ て、を実装します。 $U
最初のパラメーターは、$ \ket{s} a $ の qubit レジスタです \_ 。 2番目のパラメーターは、$ \ket{\psi} s $ の qubit レジスタです \_ 。