---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193626"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


下回っ混合状態で qubit を準備します。

Depolarizing channel $ $ \begin{align}/オメガ (\rho) \mathrel{を適用して、指定された qubit を $-bold done/$2 状態で準備します。 =} & lt ac {1} {4} \ sum_ {\ mu \ in \{ 0, 1, 2, 3 \} }-シグマ \_ {\rho} \_ ^ {-dagger}, \end{align} $ $ ここで、$ \rho \_ $ は混合状態を表す密度演算子で、$ $ は、混合の状態を表しています。 $i

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

上で説明した方法で状態を depolarized する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

混合状態 $ \ bold done/$2 では、この操作を状態に適用した結果を示していますが、この操作で行われたランダムな選択に対する期待値が暗黙的に記述されています。
したがって、1つのアプリケーションでは、この操作によって純粋な状態が純粋な状態にマップされますが、想定どおりに動作します。
具体的には、この操作をプロセス tomography で使用して、チャネルの *非 unital* コンポーネントを測定できます。