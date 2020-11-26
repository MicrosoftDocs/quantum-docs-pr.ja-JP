---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197672"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="907e6-102">LessThanLexographic 関数</span><span class="sxs-lookup"><span data-stu-id="907e6-102">LessThanLexographic function</span></span>

<span data-ttu-id="907e6-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="907e6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="907e6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="907e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="907e6-105">を実装するために使用 `LexographicComparison` します。</span><span class="sxs-lookup"><span data-stu-id="907e6-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="907e6-106">入力</span><span class="sxs-lookup"><span data-stu-id="907e6-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="907e6-107">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="907e6-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="907e6-108">左: \ []</span><span class="sxs-lookup"><span data-stu-id="907e6-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="907e6-109">right: t []</span><span class="sxs-lookup"><span data-stu-id="907e6-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="907e6-110">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="907e6-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="907e6-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="907e6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="907e6-112">&</span><span class="sxs-lookup"><span data-stu-id="907e6-112">'T</span></span>

