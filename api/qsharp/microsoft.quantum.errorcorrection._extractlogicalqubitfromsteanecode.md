---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712560"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="538a0-102">_ExtractLogicalQubitFromSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="538a0-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="538a0-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="538a0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="538a0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="538a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="538a0-105">より隣人の測定値と埋め込みの逆関数。</span><span class="sxs-lookup"><span data-stu-id="538a0-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="538a0-106">$X $-と $Z $-stabilizers は、エンコーディング回線の特定の選択によって処理されません。</span><span class="sxs-lookup"><span data-stu-id="538a0-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="538a0-107">この asymmetry は、別のより隣人抽出ルーチンにつながります。</span><span class="sxs-lookup"><span data-stu-id="538a0-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="538a0-108">より隣人を測定する方法としては、コードの状態を直接測定する方法がありますが、取り組みの目的では、論理 qubit が1つの qubit に返されます。これは、より隣人の測定値をさらに ancillas なしで実行できることです。</span><span class="sxs-lookup"><span data-stu-id="538a0-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="538a0-109">入力</span><span class="sxs-lookup"><span data-stu-id="538a0-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="538a0-110">コード: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="538a0-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="538a0-111">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="538a0-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="538a0-112">$X $-より隣人と $Z $-より隣人の論理 qubit と整数のペア。</span><span class="sxs-lookup"><span data-stu-id="538a0-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="538a0-113">これは、1つの $X $-または $Z $ error が測定されたより隣人の原因となったコード qubit のインデックスを表します。</span><span class="sxs-lookup"><span data-stu-id="538a0-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="538a0-114">解説</span><span class="sxs-lookup"><span data-stu-id="538a0-114">Remarks</span></span>

<span data-ttu-id="538a0-115">`internal`単体テストがこの操作に直接依存しているため、この操作はとマークされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="538a0-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="538a0-116">今後の改善のために、単体テストはパブリック呼び出し可能なものにのみ依存するようにリファクタリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="538a0-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="538a0-117">このルーチンは、Steane の 7 qubit コードの特定のエンコーディング回線に合わせて調整されています。エンコーディング回線を変更する場合は、より隣人の結果を異なる方法で解釈することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="538a0-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>