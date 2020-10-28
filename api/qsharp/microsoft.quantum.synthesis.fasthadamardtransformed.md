---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725183"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="5ec71-102">FastHadamardTransformed 関数</span><span class="sxs-lookup"><span data-stu-id="5ec71-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="5ec71-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5ec71-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5ec71-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ec71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ec71-105">{-1,1}Yates のメソッドを使用して、エンコードのブール関数の変換を計算します。</span><span class="sxs-lookup"><span data-stu-id="5ec71-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="5ec71-106">入力</span><span class="sxs-lookup"><span data-stu-id="5ec71-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="5ec71-107">func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5ec71-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5ec71-108">エンコードの真理表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="5ec71-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="5ec71-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5ec71-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5ec71-110">関数のスペクトル係数</span><span class="sxs-lookup"><span data-stu-id="5ec71-110">Spectral coefficients of the function</span></span>