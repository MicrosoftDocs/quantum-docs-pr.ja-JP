---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225433"
---
# <a name="blockencoding-user-defined-type"></a>BlockEncoding ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


任意の演算子が左上のブロックでエンコードされる場合の、その中の任意の演算子を指定します。

$U つまり、は、 `BlockEncoding` $H $ \ket _a $ に対応する、任意の演算子を、システムレジスタに対して作用する、$ `s` $ という補助型の上位左ブロックにエンコードすることを意味し {0} ます。 つまり、以下のようになります。

$ $ \begin{align} (\bra {0} _a \ otimes I_s) U (\ket {0} _a/otimes I_s) = H \end{align} $ $。

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

