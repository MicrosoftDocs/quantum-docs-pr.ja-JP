---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721022"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="9badc-102">LittleEndianAsBigEndian 関数</span><span class="sxs-lookup"><span data-stu-id="9badc-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="9badc-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9badc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9badc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9badc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9badc-105">Qubit の `LittleEndian` 順序を逆にして、qubit レジスタを `BigEndian` qubit レジスタに変換します。</span><span class="sxs-lookup"><span data-stu-id="9badc-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="9badc-106">入力</span><span class="sxs-lookup"><span data-stu-id="9badc-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="9badc-107">入力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9badc-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9badc-108">形式での qubit レジスタ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="9badc-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="9badc-109">出力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="9badc-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="9badc-110">形式での qubit レジスタ `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="9badc-110">Qubit register in `BigEndian` format.</span></span>