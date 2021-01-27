---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853558"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="4721a-102">AllEqualityFactB 関数</span><span class="sxs-lookup"><span data-stu-id="4721a-102">AllEqualityFactB function</span></span>

<span data-ttu-id="4721a-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4721a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4721a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4721a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4721a-105">ブール値の2つの配列が等しいことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="4721a-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4721a-106">入力</span><span class="sxs-lookup"><span data-stu-id="4721a-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="4721a-107">実際: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4721a-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4721a-108">対象のテストケースによって生成される配列。</span><span class="sxs-lookup"><span data-stu-id="4721a-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="4721a-109">必要: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4721a-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4721a-110">対象のテストケースからの予期される配列。</span><span class="sxs-lookup"><span data-stu-id="4721a-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="4721a-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4721a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4721a-112">配列が等しくない場合に出力されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4721a-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4721a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4721a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

