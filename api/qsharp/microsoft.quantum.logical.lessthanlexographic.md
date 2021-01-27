---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815644"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="02f0f-102">LessThanLexographic 関数</span><span class="sxs-lookup"><span data-stu-id="02f0f-102">LessThanLexographic function</span></span>

<span data-ttu-id="02f0f-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="02f0f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="02f0f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02f0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02f0f-105">を実装するために使用 `LexographicComparison` します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="02f0f-106">入力</span><span class="sxs-lookup"><span data-stu-id="02f0f-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="02f0f-107">比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02f0f-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="02f0f-108">左: \ []</span><span class="sxs-lookup"><span data-stu-id="02f0f-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="02f0f-109">right: t []</span><span class="sxs-lookup"><span data-stu-id="02f0f-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="02f0f-110">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02f0f-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="02f0f-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="02f0f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02f0f-112">&</span><span class="sxs-lookup"><span data-stu-id="02f0f-112">'T</span></span>

