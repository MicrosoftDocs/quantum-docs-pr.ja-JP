---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855315"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="b7a0f-102">SizeAdjustedTruthTable 関数</span><span class="sxs-lookup"><span data-stu-id="b7a0f-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="b7a0f-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b7a0f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b7a0f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7a0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7a0f-105">変数の数に基づいてブール値の配列から真理値テーブルを調整します</span><span class="sxs-lookup"><span data-stu-id="b7a0f-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="b7a0f-106">新しい配列が長さとして返され `2^numVars` ます。これは、 `table` エントリのサイズを拡張したり、要素に切り捨てたりすることが必要になる可能性が `false` `2^numVars` あります。</span><span class="sxs-lookup"><span data-stu-id="b7a0f-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b7a0f-107">入力</span><span class="sxs-lookup"><span data-stu-id="b7a0f-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="b7a0f-108">テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b7a0f-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b7a0f-109">真理値の配列としての真理値テーブル</span><span class="sxs-lookup"><span data-stu-id="b7a0f-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="b7a0f-110">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b7a0f-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b7a0f-111">変数の数</span><span class="sxs-lookup"><span data-stu-id="b7a0f-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="b7a0f-112">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b7a0f-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b7a0f-113">サイズ調整された真理値テーブル</span><span class="sxs-lookup"><span data-stu-id="b7a0f-113">Size adjusted truth table</span></span>