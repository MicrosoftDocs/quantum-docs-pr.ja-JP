---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814265"
---
# <a name="timedependentblockencoding-user-defined-type"></a>TimeDependentBlockEncoding ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


`BlockEncoding`クロックレジスタによって制御されるを表します。

$U つまり、は、 `TimeDependentBlockEncoding` クロックレジスタの状態 $ \ket{k} _d $ によって制御される、 `d` 任意の演算子 $H _k 関心があることを示す、任意の演算子関連する任意の演算子を、 `s` 補助状態 $ \ket _a $ に対応する左上のブロックにエンコードすることを意味し {0} ます。 つまり、以下のようになります。

$ $ \begin{align} (\bra {0} \_ a\ otimes I_ {ds}) U (\ket {0} \_ I_ a {ds}) = \ sum_ {k} \ket{k}\bra{k} \_ dotimes H_k。
\end{align} $ $。

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

