---
uid: Microsoft.Quantum.Canon.GrayCode
title: グレーのコード関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716163"
---
# <a name="graycode-function"></a><span data-ttu-id="2f1cb-102">グレーのコード関数</span><span class="sxs-lookup"><span data-stu-id="2f1cb-102">GrayCode function</span></span>

<span data-ttu-id="2f1cb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f1cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f1cb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f1cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f1cb-105">グレーのコードシーケンスを作成します</span><span class="sxs-lookup"><span data-stu-id="2f1cb-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="2f1cb-106">入力</span><span class="sxs-lookup"><span data-stu-id="2f1cb-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="2f1cb-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f1cb-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f1cb-108">ビット数</span><span class="sxs-lookup"><span data-stu-id="2f1cb-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="2f1cb-109">出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="2f1cb-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="2f1cb-110">タプルの配列。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-110">Array of tuples.</span></span> <span data-ttu-id="2f1cb-111">組の最初の値は、タプル内のグレーのコードシーケンスの2番目の値の値で、次の値を取得するために現在の値を変更する位置です。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>