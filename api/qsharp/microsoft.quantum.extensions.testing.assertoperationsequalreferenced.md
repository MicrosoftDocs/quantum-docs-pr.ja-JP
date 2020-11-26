---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: e6c5d4b0005cc0cf1fb62a52b4a75a0370dfa293
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212513"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="b042e-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="b042e-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="b042e-103">名前空間: [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing) .. 拡張子</span><span class="sxs-lookup"><span data-stu-id="b042e-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="b042e-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="b042e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="b042e-105">AssertOperationsEqualReferenced は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="b042e-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="b042e-106">代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b042e-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="b042e-107">@"microsoft.quantum.diagnostics.assertoperationsequalreferenced" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b042e-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="b042e-108">この操作の引数の順序が変更されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b042e-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="b042e-109">入力</span><span class="sxs-lookup"><span data-stu-id="b042e-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="b042e-110">実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b042e-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="b042e-111">想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="b042e-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="b042e-112">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b042e-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b042e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b042e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

