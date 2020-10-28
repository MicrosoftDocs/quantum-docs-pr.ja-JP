---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712196"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="9cafa-102">RecoveryFn ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="9cafa-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="9cafa-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9cafa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9cafa-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cafa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cafa-105">エラーより隣人を、検出されたエラーを修正する一連の操作にマップする関数の型 `Pauli[]` 。</span><span class="sxs-lookup"><span data-stu-id="9cafa-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

