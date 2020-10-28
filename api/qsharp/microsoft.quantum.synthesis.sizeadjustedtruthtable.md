---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725472"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="3c4fe-102">SizeAdjustedTruthTable 関数</span><span class="sxs-lookup"><span data-stu-id="3c4fe-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="3c4fe-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3c4fe-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3c4fe-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c4fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c4fe-105">変数の数に基づいてブール値の配列から真理値テーブルを調整します</span><span class="sxs-lookup"><span data-stu-id="3c4fe-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="3c4fe-106">新しい配列が長さとして返され `2^numVars` ます。これは、 `table` エントリのサイズを拡張したり、要素に切り捨てたりすることが必要になる可能性が `false` `2^numVars` あります。</span><span class="sxs-lookup"><span data-stu-id="3c4fe-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="3c4fe-107">入力</span><span class="sxs-lookup"><span data-stu-id="3c4fe-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="3c4fe-108">テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3c4fe-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3c4fe-109">真理値の配列としての真理値テーブル</span><span class="sxs-lookup"><span data-stu-id="3c4fe-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="3c4fe-110">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c4fe-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c4fe-111">変数の数</span><span class="sxs-lookup"><span data-stu-id="3c4fe-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="3c4fe-112">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3c4fe-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3c4fe-113">サイズ調整された真理値テーブル</span><span class="sxs-lookup"><span data-stu-id="3c4fe-113">Size adjusted truth table</span></span>