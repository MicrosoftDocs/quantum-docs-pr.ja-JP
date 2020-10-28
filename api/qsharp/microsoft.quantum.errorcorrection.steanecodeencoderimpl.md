---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712187"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="8747a-102">SteaneCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="8747a-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="8747a-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8747a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8747a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8747a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8747a-105">Steane コードエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。</span><span class="sxs-lookup"><span data-stu-id="8747a-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8747a-106">入力</span><span class="sxs-lookup"><span data-stu-id="8747a-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="8747a-107">データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8747a-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8747a-108">入力 qubit である1つの qubit を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="8747a-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="8747a-109">スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8747a-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8747a-110">冗長性を追加する6つの qubits を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="8747a-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8747a-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8747a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

