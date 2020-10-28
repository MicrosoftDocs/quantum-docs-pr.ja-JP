---
uid: Microsoft.Quantum.Synthesis.Encoded
title: エンコードされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725206"
---
# <a name="encoded-function"></a><span data-ttu-id="036ab-102">エンコードされた関数</span><span class="sxs-lookup"><span data-stu-id="036ab-102">Encoded function</span></span>

<span data-ttu-id="036ab-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="036ab-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="036ab-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="036ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="036ab-105">コーディングでの真実テーブルのエンコード {1,-1}</span><span class="sxs-lookup"><span data-stu-id="036ab-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="036ab-106">入力</span><span class="sxs-lookup"><span data-stu-id="036ab-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="036ab-107">テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="036ab-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="036ab-108">真理値の配列としての真理値テーブル</span><span class="sxs-lookup"><span data-stu-id="036ab-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="036ab-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="036ab-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="036ab-110">整数の配列としての真理値テーブル {1,-1}</span><span class="sxs-lookup"><span data-stu-id="036ab-110">Truth table as array of {1,-1} integers</span></span>