---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714828"
---
# <a name="isnotzero-function"></a><span data-ttu-id="c0bf2-102">IsNotZero 関数</span><span class="sxs-lookup"><span data-stu-id="c0bf2-102">IsNotZero function</span></span>

<span data-ttu-id="c0bf2-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c0bf2-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="c0bf2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0bf2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0bf2-105">`Double`数値が約0以外であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0bf2-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c0bf2-106">入力</span><span class="sxs-lookup"><span data-stu-id="c0bf2-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="c0bf2-107">数値: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0bf2-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0bf2-108">確認する数値</span><span class="sxs-lookup"><span data-stu-id="c0bf2-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="c0bf2-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c0bf2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c0bf2-110">`number`の値がを超える絶対値を持つ場合に true を返し `1e-15` ます。</span><span class="sxs-lookup"><span data-stu-id="c0bf2-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>