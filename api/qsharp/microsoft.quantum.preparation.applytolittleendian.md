---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: ApplyToLittleEndian ディアン操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724105"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="45cb2-102">ApplyToLittleEndian ディアン操作</span><span class="sxs-lookup"><span data-stu-id="45cb2-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="45cb2-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="45cb2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="45cb2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45cb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45cb2-105">リトルエンディアンレジスタを作成する、基になる qubits に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="45cb2-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="45cb2-106">この操作は内部としてマークされています。リトルエンディアンレジスタは "不透明" になるため、これが実装の詳細であることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="45cb2-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="45cb2-107">入力</span><span class="sxs-lookup"><span data-stu-id="45cb2-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="45cb2-108">bareOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞と Ctl</span><span class="sxs-lookup"><span data-stu-id="45cb2-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="45cb2-109">register: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45cb2-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="45cb2-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45cb2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

