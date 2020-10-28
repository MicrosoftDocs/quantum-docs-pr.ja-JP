---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724296"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パック [](https://nuget.org/packages/)


決定的な状態の準備のための oracle を表します。

Oracle $O $ への入力は次のとおりです。

- 目的のクォンタム状態 $ \ket{\psi} s $ を格納するレジスタ \_ 。

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>解説

$O \ket = \ket{\psi} $ によって定義されたこの oracle {0} は、コンピューティングベースの状態 $ \ket $ で動作し、 {0} 状態 $ \ket{\psi} $ を作成します。
最初のパラメーターは $ \ket{\psi} $ の qubit レジスタです。