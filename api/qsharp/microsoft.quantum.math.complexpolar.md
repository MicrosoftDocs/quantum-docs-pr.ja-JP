---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210983"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="c4aa2-102">ComplexPolar ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="c4aa2-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="c4aa2-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c4aa2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c4aa2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4aa2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4aa2-105">極座標形式の複素数を表します。</span><span class="sxs-lookup"><span data-stu-id="c4aa2-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="c4aa2-106">複素数の極座標表現は $c = r e ^ {i t} $ です。</span><span class="sxs-lookup"><span data-stu-id="c4aa2-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="c4aa2-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="c4aa2-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="c4aa2-108">マグニチュード: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4aa2-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4aa2-109">$C $ の $0 $r の絶対値。</span><span class="sxs-lookup"><span data-stu-id="c4aa2-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="c4aa2-110">引数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4aa2-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4aa2-111">フェーズ $t、$c $ の \mathbb R $。</span><span class="sxs-lookup"><span data-stu-id="c4aa2-111">The phase $t \in \mathbb R$ of $c$.</span></span>