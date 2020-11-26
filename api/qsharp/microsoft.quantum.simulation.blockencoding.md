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
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="9e28e-102">BlockEncoding ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="9e28e-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="9e28e-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9e28e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9e28e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e28e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e28e-105">任意の演算子が左上のブロックでエンコードされる場合の、その中の任意の演算子を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e28e-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="9e28e-106">$U つまり、は、 `BlockEncoding` $H $ \ket _a $ に対応する、任意の演算子を、システムレジスタに対して作用する、$ `s` $ という補助型の上位左ブロックにエンコードすることを意味し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="9e28e-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="9e28e-107">つまり、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="9e28e-107">That is,</span></span>

<span data-ttu-id="9e28e-108">$ $ \begin{align} (\bra {0} _a \ otimes I_s) U (\ket {0} _a/otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="9e28e-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

