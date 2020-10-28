---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709961"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="8c3b4-102">LessThanLexographic 関数</span><span class="sxs-lookup"><span data-stu-id="8c3b4-102">LessThanLexographic function</span></span>

<span data-ttu-id="8c3b4-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8c3b4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8c3b4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c3b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c3b4-105">を実装するために使用 `LexographicComparison` します。</span><span class="sxs-lookup"><span data-stu-id="8c3b4-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="8c3b4-106">入力</span><span class="sxs-lookup"><span data-stu-id="8c3b4-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="8c3b4-107">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8c3b4-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="8c3b4-108">左: \ []</span><span class="sxs-lookup"><span data-stu-id="8c3b4-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="8c3b4-109">right: t []</span><span class="sxs-lookup"><span data-stu-id="8c3b4-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="8c3b4-110">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8c3b4-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c3b4-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c3b4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c3b4-112">&</span><span class="sxs-lookup"><span data-stu-id="8c3b4-112">'T</span></span>

