---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847345"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="47ca5-102">ComplexPolar ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="47ca5-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="47ca5-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="47ca5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="47ca5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47ca5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47ca5-105">極座標形式の複素数を表します。</span><span class="sxs-lookup"><span data-stu-id="47ca5-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="47ca5-106">複素数の極座標表現は $c = r e ^ {i t} $ です。</span><span class="sxs-lookup"><span data-stu-id="47ca5-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="47ca5-107">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="47ca5-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="47ca5-108">マグニチュード: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="47ca5-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="47ca5-109">$C $ の $0 $r の絶対値。</span><span class="sxs-lookup"><span data-stu-id="47ca5-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="47ca5-110">引数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="47ca5-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="47ca5-111">フェーズ $t、$c $ の \mathbb R $。</span><span class="sxs-lookup"><span data-stu-id="47ca5-111">The phase $t \in \mathbb R$ of $c$.</span></span>