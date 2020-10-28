---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712140"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="611af-102">SteaneCodeRecoveryFns 関数</span><span class="sxs-lookup"><span data-stu-id="611af-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="611af-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="611af-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="611af-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="611af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="611af-105">⟦7、1、3⟧ Steane 量子コードの安定板グループの X 部と Z 部を組み合わせたデコーダーです。</span><span class="sxs-lookup"><span data-stu-id="611af-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="611af-106">出力: ([recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)、[recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span><span class="sxs-lookup"><span data-stu-id="611af-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="611af-107">`RecoveryFn`より隣人の測定値を受け取り、 `Result[]` `Pauli[]` 検出されたエラーを修正する操作を返す、型の関数のタプル。</span><span class="sxs-lookup"><span data-stu-id="611af-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="611af-108">参照</span><span class="sxs-lookup"><span data-stu-id="611af-108">See Also</span></span>

- [<span data-ttu-id="611af-109">SteaneCodeRecoveryX を修正します。</span><span class="sxs-lookup"><span data-stu-id="611af-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="611af-110">SteaneCodeRecoveryZ を修正します。</span><span class="sxs-lookup"><span data-stu-id="611af-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)