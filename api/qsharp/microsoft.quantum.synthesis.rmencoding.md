---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855340"
---
# <a name="rmencoding-function"></a><span data-ttu-id="7d79d-102">RMEncoding 関数</span><span class="sxs-lookup"><span data-stu-id="7d79d-102">RMEncoding function</span></span>

<span data-ttu-id="7d79d-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7d79d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7d79d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d79d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d79d-105">{-1,1} ブール値の真偽値のコーディング</span><span class="sxs-lookup"><span data-stu-id="7d79d-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="7d79d-106">入力</span><span class="sxs-lookup"><span data-stu-id="7d79d-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="7d79d-107">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d79d-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d79d-108">ブール値</span><span class="sxs-lookup"><span data-stu-id="7d79d-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="7d79d-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d79d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d79d-110">が false の場合は1。それ以外の場合は `b` -1。</span><span class="sxs-lookup"><span data-stu-id="7d79d-110">1, if `b` is false, otherwise -1</span></span>