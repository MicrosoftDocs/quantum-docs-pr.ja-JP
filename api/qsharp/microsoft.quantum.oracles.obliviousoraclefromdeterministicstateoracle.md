---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722224"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="824de-102">ObliviousOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="824de-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="824de-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="824de-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="824de-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="824de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="824de-105">Oracles `DeterministicStateOracle` とを結合し `ObliviousOracle` ます。</span><span class="sxs-lookup"><span data-stu-id="824de-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="824de-106">入力</span><span class="sxs-lookup"><span data-stu-id="824de-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="824de-107">ブランコ Illaoracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="824de-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="824de-108">登録 $a $ で動作する型の状態準備 oracle $A $ `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="824de-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="824de-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="824de-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="824de-110">`ObliviousOracle`Register $a, s $ に共同で作用する型の oracle $U $。</span><span class="sxs-lookup"><span data-stu-id="824de-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="824de-111">出力: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="824de-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="824de-112">Oracle $O = UA $ 型 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="824de-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="824de-113">参照</span><span class="sxs-lookup"><span data-stu-id="824de-113">See Also</span></span>

- [<span data-ttu-id="824de-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="824de-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="824de-115">Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="824de-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)