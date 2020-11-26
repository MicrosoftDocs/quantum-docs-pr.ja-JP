---
uid: Microsoft.Quantum.Canon.GrayCode
title: グレーのコード関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206886"
---
# <a name="graycode-function"></a><span data-ttu-id="c1eb9-102">グレーのコード関数</span><span class="sxs-lookup"><span data-stu-id="c1eb9-102">GrayCode function</span></span>

<span data-ttu-id="c1eb9-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1eb9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1eb9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1eb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1eb9-105">グレーのコードシーケンスを作成します</span><span class="sxs-lookup"><span data-stu-id="c1eb9-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c1eb9-106">入力</span><span class="sxs-lookup"><span data-stu-id="c1eb9-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="c1eb9-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1eb9-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1eb9-108">ビット数</span><span class="sxs-lookup"><span data-stu-id="c1eb9-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="c1eb9-109">出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c1eb9-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c1eb9-110">タプルの配列。</span><span class="sxs-lookup"><span data-stu-id="c1eb9-110">Array of tuples.</span></span> <span data-ttu-id="c1eb9-111">組の最初の値は、タプル内のグレーのコードシーケンスの2番目の値の値で、次の値を取得するために現在の値を変更する位置です。</span><span class="sxs-lookup"><span data-stu-id="c1eb9-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>