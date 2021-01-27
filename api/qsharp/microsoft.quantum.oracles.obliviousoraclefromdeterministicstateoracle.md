---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: c7aa80feda67d68216f318073ee8c6a5eb0653c0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854527"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="dc9a7-102">ObliviousOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="dc9a7-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="dc9a7-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="dc9a7-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="dc9a7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc9a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc9a7-105">Oracles `DeterministicStateOracle` とを結合し `ObliviousOracle` ます。</span><span class="sxs-lookup"><span data-stu-id="dc9a7-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="dc9a7-106">入力</span><span class="sxs-lookup"><span data-stu-id="dc9a7-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="dc9a7-107">ブランコ Illaoracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="dc9a7-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="dc9a7-108">登録 $a $ で動作する型の状態準備 oracle $A $ `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="dc9a7-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="dc9a7-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="dc9a7-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="dc9a7-110">`ObliviousOracle`Register $a, s $ に共同で作用する型の oracle $U $。</span><span class="sxs-lookup"><span data-stu-id="dc9a7-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="dc9a7-111">出力: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="dc9a7-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="dc9a7-112">Oracle $O = UA $ 型 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="dc9a7-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc9a7-113">参照</span><span class="sxs-lookup"><span data-stu-id="dc9a7-113">See Also</span></span>

- [<span data-ttu-id="dc9a7-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="dc9a7-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="dc9a7-115">Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="dc9a7-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)