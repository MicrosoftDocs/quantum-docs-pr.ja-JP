---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 1f4d98006677dc532d45ffb797fe0a8e05496640
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820104"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="85861-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="85861-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="85861-103">名前空間: [Microsoft.](xref:Microsoft.Quantum.Extensions.Testing) .. 拡張子</span><span class="sxs-lookup"><span data-stu-id="85861-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="85861-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="85861-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="85861-105">AssertOperationsEqualReferenced は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="85861-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="85861-106">代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="85861-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="85861-107">@"microsoft.quantum.diagnostics.assertoperationsequalreferenced" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="85861-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="85861-108">この操作の引数の順序が変更されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="85861-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="85861-109">入力</span><span class="sxs-lookup"><span data-stu-id="85861-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="85861-110">実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85861-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="85861-111">想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="85861-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="85861-112">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85861-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="85861-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85861-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

