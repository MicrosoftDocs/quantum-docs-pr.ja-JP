---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857628"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="debfb-102">BlockEncoding ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="debfb-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="debfb-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="debfb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="debfb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="debfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="debfb-105">任意の演算子が左上のブロックでエンコードされる場合の、その中の任意の演算子を指定します。</span><span class="sxs-lookup"><span data-stu-id="debfb-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="debfb-106">$U つまり、は、 `BlockEncoding` $H $ \ket _a $ に対応する、任意の演算子を、システムレジスタに対して作用する、$ `s` $ という補助型の上位左ブロックにエンコードすることを意味し {0} ます。</span><span class="sxs-lookup"><span data-stu-id="debfb-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="debfb-107">つまり、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="debfb-107">That is,</span></span>

<span data-ttu-id="debfb-108">$ $ \begin{align} (\bra {0} _a \ otimes I_s) U (\ket {0} _a/otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="debfb-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

