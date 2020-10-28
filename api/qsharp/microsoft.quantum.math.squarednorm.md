---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725024"
---
# <a name="squarednorm-function"></a><span data-ttu-id="2d875-102">SquaredNorm 関数</span><span class="sxs-lookup"><span data-stu-id="2d875-102">SquaredNorm function</span></span>

<span data-ttu-id="2d875-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2d875-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2d875-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d875-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d875-105">ベクターの2乗値を返します。</span><span class="sxs-lookup"><span data-stu-id="2d875-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="2d875-106">説明</span><span class="sxs-lookup"><span data-stu-id="2d875-106">Description</span></span>

<span data-ttu-id="2d875-107">ベクターの2乗を返します。つまり、入力 $ \vec{x} $ を指定すると、$ \ sum_i x_i ^ 2 $ が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d875-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="2d875-108">入力</span><span class="sxs-lookup"><span data-stu-id="2d875-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="2d875-109">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2d875-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2d875-110">2乗値が返されるベクトル。</span><span class="sxs-lookup"><span data-stu-id="2d875-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="2d875-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d875-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d875-112">の2乗の二乗 `array` 。</span><span class="sxs-lookup"><span data-stu-id="2d875-112">The squared 2-norm of `array`.</span></span>