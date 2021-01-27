---
uid: Microsoft.Quantum.Canon.GrayCode
title: グレーのコード関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840494"
---
# <a name="graycode-function"></a><span data-ttu-id="ef106-102">グレーのコード関数</span><span class="sxs-lookup"><span data-stu-id="ef106-102">GrayCode function</span></span>

<span data-ttu-id="ef106-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef106-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef106-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef106-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef106-105">グレーのコードシーケンスを作成します</span><span class="sxs-lookup"><span data-stu-id="ef106-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="ef106-106">入力</span><span class="sxs-lookup"><span data-stu-id="ef106-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="ef106-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ef106-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ef106-108">ビット数</span><span class="sxs-lookup"><span data-stu-id="ef106-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="ef106-109">出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="ef106-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="ef106-110">タプルの配列。</span><span class="sxs-lookup"><span data-stu-id="ef106-110">Array of tuples.</span></span> <span data-ttu-id="ef106-111">組の最初の値は、タプル内のグレーのコードシーケンスの2番目の値の値で、次の値を取得するために現在の値を変更する位置です。</span><span class="sxs-lookup"><span data-stu-id="ef106-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="ef106-112">例</span><span class="sxs-lookup"><span data-stu-id="ef106-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```