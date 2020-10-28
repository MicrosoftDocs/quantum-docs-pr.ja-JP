---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725477"
---
# <a name="rmencoding-function"></a><span data-ttu-id="4e899-102">RMEncoding 関数</span><span class="sxs-lookup"><span data-stu-id="4e899-102">RMEncoding function</span></span>

<span data-ttu-id="4e899-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4e899-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4e899-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e899-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e899-105">{-1,1} ブール値の真偽値のコーディング</span><span class="sxs-lookup"><span data-stu-id="4e899-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="4e899-106">入力</span><span class="sxs-lookup"><span data-stu-id="4e899-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="4e899-107">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4e899-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4e899-108">ブール値</span><span class="sxs-lookup"><span data-stu-id="4e899-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="4e899-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e899-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e899-110">が false の場合は1。それ以外の場合は `b` -1。</span><span class="sxs-lookup"><span data-stu-id="4e899-110">1, if `b` is false, otherwise -1</span></span>