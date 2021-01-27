---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842589"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


決定的な状態の準備のための oracle を表します。

Oracle $O $ への入力は次のとおりです。

- 目的のクォンタム状態 $ \ket{\psi} s $ を格納するレジスタ \_ 。

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>解説

$O \ket = \ket{\psi} $ によって定義されたこの oracle {0} は、コンピューティングベースの状態 $ \ket $ で動作し、 {0} 状態 $ \ket{\psi} $ を作成します。
最初のパラメーターは $ \ket{\psi} $ の qubit レジスタです。