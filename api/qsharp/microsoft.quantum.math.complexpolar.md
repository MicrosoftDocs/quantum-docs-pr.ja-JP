---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709648"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="e1b84-102">ComplexPolar ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="e1b84-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="e1b84-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e1b84-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e1b84-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1b84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1b84-105">極座標形式の複素数を表します。</span><span class="sxs-lookup"><span data-stu-id="e1b84-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="e1b84-106">複素数の極座標表現は $c = r e ^ {i t} $ です。</span><span class="sxs-lookup"><span data-stu-id="e1b84-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="e1b84-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="e1b84-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="e1b84-108">マグニチュード: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e1b84-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e1b84-109">$C $ の $0 $r の絶対値。</span><span class="sxs-lookup"><span data-stu-id="e1b84-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="e1b84-110">引数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e1b84-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e1b84-111">フェーズ $t、$c $ の \mathbb R $。</span><span class="sxs-lookup"><span data-stu-id="e1b84-111">The phase $t \in \mathbb R$ of $c$.</span></span>