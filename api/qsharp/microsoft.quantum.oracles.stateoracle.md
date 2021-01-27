---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854466"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


状態の準備のための oracle を表します。

Oracle $O $ への入力は次のとおりです。

- フラグ qubit $f $ にインデックスを付ける整数。
- 必要なクォンタムの状態 $ \ket{\psi} s $ を格納する $s $ がシステムに登録され \_ ます。

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>解説

$ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket fcドット $ $ によって定義されているこの oracle {0} \_ は、計算ベースの状態 $ \ket {0} \_ {f} \ket s $ を使用して、 {0} \_ \_ $ \ket{\psi} {1} f $ によってフラグが設定されたターゲットの状態 $ \ket s $ \_
最初のパラメーターは、$ \ket f $ の qubit レジスタのインデックスです {0} \_ 。 2番目のパラメーターには、両方のレジスタがあります。