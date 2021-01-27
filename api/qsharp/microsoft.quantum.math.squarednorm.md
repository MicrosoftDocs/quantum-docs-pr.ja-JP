---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848209"
---
# <a name="squarednorm-function"></a><span data-ttu-id="994f0-102">SquaredNorm 関数</span><span class="sxs-lookup"><span data-stu-id="994f0-102">SquaredNorm function</span></span>

<span data-ttu-id="994f0-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="994f0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="994f0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="994f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="994f0-105">ベクターの2乗値を返します。</span><span class="sxs-lookup"><span data-stu-id="994f0-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="994f0-106">説明</span><span class="sxs-lookup"><span data-stu-id="994f0-106">Description</span></span>

<span data-ttu-id="994f0-107">ベクターの2乗を返します。つまり、入力 $ \vec{x} $ を指定すると、$ \ sum_i x_i ^ 2 $ が返されます。</span><span class="sxs-lookup"><span data-stu-id="994f0-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="994f0-108">入力</span><span class="sxs-lookup"><span data-stu-id="994f0-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="994f0-109">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="994f0-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="994f0-110">2乗値が返されるベクトル。</span><span class="sxs-lookup"><span data-stu-id="994f0-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="994f0-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="994f0-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="994f0-112">の2乗の二乗 `array` 。</span><span class="sxs-lookup"><span data-stu-id="994f0-112">The squared 2-norm of `array`.</span></span>