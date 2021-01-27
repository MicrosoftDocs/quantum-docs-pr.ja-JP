---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855451"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="94104-102">FastHadamardTransformed 関数</span><span class="sxs-lookup"><span data-stu-id="94104-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="94104-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="94104-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="94104-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94104-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94104-105">{-1,1}Yates のメソッドを使用して、エンコードのブール関数の変換を計算します。</span><span class="sxs-lookup"><span data-stu-id="94104-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="94104-106">入力</span><span class="sxs-lookup"><span data-stu-id="94104-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="94104-107">func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="94104-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="94104-108">エンコードの真理表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="94104-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="94104-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="94104-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="94104-110">関数のスペクトル係数</span><span class="sxs-lookup"><span data-stu-id="94104-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="94104-111">例</span><span class="sxs-lookup"><span data-stu-id="94104-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```