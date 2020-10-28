---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721334"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="c5af8-102">BigEndianAsLittleEndian 関数</span><span class="sxs-lookup"><span data-stu-id="c5af8-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="c5af8-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5af8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5af8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5af8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5af8-105">Qubit の `BigEndian` 順序を逆にして、qubit レジスタを `LittleEndian` qubit レジスタに変換します。</span><span class="sxs-lookup"><span data-stu-id="c5af8-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="c5af8-106">入力</span><span class="sxs-lookup"><span data-stu-id="c5af8-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="c5af8-107">入力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c5af8-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c5af8-108">形式での qubit レジスタ `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="c5af8-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="c5af8-109">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5af8-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5af8-110">形式での qubit レジスタ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="c5af8-110">Qubit register in `LittleEndian` format.</span></span>