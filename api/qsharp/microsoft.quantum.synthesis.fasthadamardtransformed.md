---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203095"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="69c8f-102">FastHadamardTransformed 関数</span><span class="sxs-lookup"><span data-stu-id="69c8f-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="69c8f-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="69c8f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="69c8f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c8f-105">{-1,1}Yates のメソッドを使用して、エンコードのブール関数の変換を計算します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="69c8f-106">入力</span><span class="sxs-lookup"><span data-stu-id="69c8f-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="69c8f-107">func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="69c8f-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="69c8f-108">エンコードの真理表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="69c8f-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="69c8f-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="69c8f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="69c8f-110">関数のスペクトル係数</span><span class="sxs-lookup"><span data-stu-id="69c8f-110">Spectral coefficients of the function</span></span>