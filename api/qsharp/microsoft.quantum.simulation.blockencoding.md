---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722691"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="f4aec-102">BlockEncoding ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="f4aec-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="f4aec-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f4aec-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f4aec-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4aec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4aec-105">任意の演算子が左上のブロックでエンコードされる場合の、その中の任意の演算子を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4aec-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="f4aec-106">$U つまり、は、 `BlockEncoding` $H $ \ket _a $ に対応する、任意の演算子を、システムレジスタに対して作用する、$ `s` $ という補助型の上位左ブロックにエンコードすることを意味し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="f4aec-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="f4aec-107">つまり、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="f4aec-107">That is,</span></span>

<span data-ttu-id="f4aec-108">$ $ \begin{align} (\bra {0} _a \ otimes I_s) U (\ket {0} _a/otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="f4aec-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

