---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204064"
---
# <a name="isnotzero-function"></a><span data-ttu-id="02a8a-102">IsNotZero 関数</span><span class="sxs-lookup"><span data-stu-id="02a8a-102">IsNotZero function</span></span>

<span data-ttu-id="02a8a-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="02a8a-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="02a8a-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="02a8a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="02a8a-105">`Double`数値が約0以外であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="02a8a-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="02a8a-106">入力</span><span class="sxs-lookup"><span data-stu-id="02a8a-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="02a8a-107">数値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="02a8a-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="02a8a-108">確認する数値</span><span class="sxs-lookup"><span data-stu-id="02a8a-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="02a8a-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02a8a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="02a8a-110">`number`の値がを超える絶対値を持つ場合に true を返し `1e-15` ます。</span><span class="sxs-lookup"><span data-stu-id="02a8a-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>