---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709751"
---
# <a name="inputencoder-function"></a><span data-ttu-id="8bc6c-102">InputEncoder 関数</span><span class="sxs-lookup"><span data-stu-id="8bc6c-102">InputEncoder function</span></span>

<span data-ttu-id="8bc6c-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8bc6c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8bc6c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bc6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bc6c-105">係数と許容範囲を指定すると、は、各係数を計算ベース状態の対応する振幅として準備する状態準備操作を返します。</span><span class="sxs-lookup"><span data-stu-id="8bc6c-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="8bc6c-106">入力</span><span class="sxs-lookup"><span data-stu-id="8bc6c-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="8bc6c-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8bc6c-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8bc6c-108">入力状態にエンコードされる係数。</span><span class="sxs-lookup"><span data-stu-id="8bc6c-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="8bc6c-109">出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="8bc6c-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="8bc6c-110">指定された係数を特定のレジスタの入力状態として準備する状態準備操作。</span><span class="sxs-lookup"><span data-stu-id="8bc6c-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>