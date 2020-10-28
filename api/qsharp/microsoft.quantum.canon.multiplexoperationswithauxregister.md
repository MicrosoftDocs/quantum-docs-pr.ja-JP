---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: MultiplexOperationsWithAuxRegister 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: f6a90657324f8528aaa2e9e511a7f8cbcd2f540f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715794"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="57c93-102">MultiplexOperationsWithAuxRegister 操作</span><span class="sxs-lookup"><span data-stu-id="57c93-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="57c93-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57c93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57c93-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57c93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57c93-105">MultiplexOperations の実装手順。</span><span class="sxs-lookup"><span data-stu-id="57c93-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="57c93-106">入力</span><span class="sxs-lookup"><span data-stu-id="57c93-106">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="57c93-107">unitaries: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="57c93-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="57c93-108">auxillaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="57c93-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="57c93-109">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="57c93-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="57c93-110">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="57c93-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="57c93-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57c93-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57c93-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="57c93-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57c93-113">&</span><span class="sxs-lookup"><span data-stu-id="57c93-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="57c93-114">参照</span><span class="sxs-lookup"><span data-stu-id="57c93-114">See Also</span></span>

- [<span data-ttu-id="57c93-115">Microsoft. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="57c93-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)