---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: b6523c0d8f3e6d0ac4ec63234a7de342f8d6c065
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857901"
---
# <a name="idxtocoeff-function"></a><span data-ttu-id="de8ac-102">IdxToCoeff 関数</span><span class="sxs-lookup"><span data-stu-id="de8ac-102">IdxToCoeff function</span></span>

<span data-ttu-id="de8ac-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="de8ac-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="de8ac-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de8ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de8ac-105">の実装で使用されます。 `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="de8ac-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a><span data-ttu-id="de8ac-106">入力</span><span class="sxs-lookup"><span data-stu-id="de8ac-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="de8ac-107">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de8ac-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="de8ac-108">genfun: [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="de8ac-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtocoeff--generatorindex---double"></a><span data-ttu-id="de8ac-109">genIdxToCoeff: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de8ac-109">genIdxToCoeff : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="de8ac-110">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de8ac-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="see-also"></a><span data-ttu-id="de8ac-111">参照</span><span class="sxs-lookup"><span data-stu-id="de8ac-111">See Also</span></span>

- [<span data-ttu-id="de8ac-112">Microsoft... シミュレーションのエンコード</span><span class="sxs-lookup"><span data-stu-id="de8ac-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)