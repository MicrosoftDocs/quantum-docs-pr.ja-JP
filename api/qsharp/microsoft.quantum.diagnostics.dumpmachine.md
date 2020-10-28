---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712873"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="3f57b-102">DumpMachine 関数</span><span class="sxs-lookup"><span data-stu-id="3f57b-102">DumpMachine function</span></span>

<span data-ttu-id="3f57b-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3f57b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3f57b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f57b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f57b-105">現在のターゲットコンピューターの状態をダンプします。</span><span class="sxs-lookup"><span data-stu-id="3f57b-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="3f57b-106">入力</span><span class="sxs-lookup"><span data-stu-id="3f57b-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="3f57b-107">場所: \</span><span class="sxs-lookup"><span data-stu-id="3f57b-107">location : 'T</span></span>

<span data-ttu-id="3f57b-108">コンピューターのダンプを生成する場所に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f57b-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f57b-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f57b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="3f57b-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="3f57b-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3f57b-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f57b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3f57b-112">&</span><span class="sxs-lookup"><span data-stu-id="3f57b-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3f57b-113">解説</span><span class="sxs-lookup"><span data-stu-id="3f57b-113">Remarks</span></span>

<span data-ttu-id="3f57b-114">このメソッドを使用すると、ターゲットコンピューターの現在の状態に関する情報をファイルまたはその他の場所にダンプできます。</span><span class="sxs-lookup"><span data-stu-id="3f57b-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="3f57b-115">生成される実際の情報とのセマンティクス `location` は、各ターゲットコンピューターに固有です。</span><span class="sxs-lookup"><span data-stu-id="3f57b-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="3f57b-116">ただし、空のタプルを場所として指定 `()` する () か、パラメーターを省略するだけで、 `location` 通常はコンソールに出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="3f57b-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="3f57b-117">Quantum 開発キットの一部として配布されたローカルの完全な状態シミュレーターでは、このメソッドは、wave 関数を1次元の複素数の配列として書き込むファイルのパスを含む文字列を想定しています。各要素は、対応する状態を測定する確率の振幅を表します。</span><span class="sxs-lookup"><span data-stu-id="3f57b-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>