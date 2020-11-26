---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 0f22bcbf74a33b1501acf9222d6dc6327b16bbbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212547"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="2a641-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="2a641-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="2a641-103">名前空間: [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing) .. 拡張子</span><span class="sxs-lookup"><span data-stu-id="2a641-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="2a641-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="2a641-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="2a641-105">AssertOperationsEqualInPlace は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="2a641-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="2a641-106">代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2a641-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="2a641-107">@"microsoft.quantum.diagnostics.assertoperationsequalinplace" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2a641-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="2a641-108">この操作の引数の順序が変更されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a641-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="2a641-109">入力</span><span class="sxs-lookup"><span data-stu-id="2a641-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="2a641-110">実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a641-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="2a641-111">想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="2a641-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="2a641-112">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a641-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2a641-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a641-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

