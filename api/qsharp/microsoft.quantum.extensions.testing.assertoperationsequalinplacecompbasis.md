---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlaceCompBasis has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplaceCompBasis".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 35816ecd14cdd87a905c5e3b6ce5ff32edadaca5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711636"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="8bd73-102">AssertOperationsEqualInPlaceCompBasis 操作</span><span class="sxs-lookup"><span data-stu-id="8bd73-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="8bd73-103">名前空間: [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing) .. 拡張子</span><span class="sxs-lookup"><span data-stu-id="8bd73-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="8bd73-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bd73-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="8bd73-105">AssertOperationsEqualInPlaceCompBasis は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="8bd73-105">AssertOperationsEqualInPlaceCompBasis has been deprecated.</span></span> <span data-ttu-id="8bd73-106">代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8bd73-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> instead.</span></span>
>
> <span data-ttu-id="8bd73-107">@"microsoft.quantum.diagnostics.assertoperationsequalinplaceCompBasis" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8bd73-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplaceCompBasis".</span></span>
> <span data-ttu-id="8bd73-108">この操作の引数の順序が変更されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8bd73-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlaceCompBasis (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="8bd73-109">入力</span><span class="sxs-lookup"><span data-stu-id="8bd73-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="8bd73-110">実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bd73-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="8bd73-111">想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="8bd73-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="8bd73-112">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8bd73-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="8bd73-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bd73-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

